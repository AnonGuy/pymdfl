# PyMDFL
A command-line application to generate data packs based on [CRISPYRice](https://github.com/CRISPYricePC/MDFL-Spec/blob/master/spec.md)'s MDFL specification.


## Usage
`mdfl --help` will output usage information:
```
Command-line tool for parsing MDFL.

Usage:
    mdfl <script>
    mdfl -h | --help
    mdfl --versio
```

The `<script>` argument specifies a file that conforms to the MDFL spec. For example, given a file `gems.mdfl`:
```
namespace diamonds {
  // Namespace for obtaining diamonds.

  fun get {
    // Give the caller a diamond.
    give @s minecraft:diamond;
  }
}

namespace emeralds {
  // Namespace for obtaining emeralds.

  fun get {
    // Give the caller an emerald.
    give @s minecraft:emerald;
  }
}
```
Run `mdfl gems.mdfl` and enter a description for your data pack.
```
$ mdfl gems.mdfl
Description of gems: All your gems are belong to @s
```
This will generate a zip file `gems.zip` with the following structure:
```
├── data
│  ├── emeralds
│  │  └── functions
│  │     └── get.mcfunction
│  └── diamonds
│     └── functions
│        └── get.mcfunction
└── pack.mcmeta
```