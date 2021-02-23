[Back](README.md)

# Conventions

## GIT
---
>\<type\> = {fix / merge / comment / code / doc / test / review / indentation}

### Branch

  - **Master Branch** `IMPORTANT` Only the project leader can manipulate this branch (permissions)
  - **One branch master by feature** : 'namefeature-main'
  - If you need some **sub-branchs of feature branch** (not too much), create one :
    >feature-\<type\>

### Commits
  - **Good description** :
    >fullNameBranch : short description in English

  - `GitKraken`  : there are two fields, the first for the name and the second for your explications/description

### Other
  - When **you have finished to code** on sub-branch and that the code is functional then you can merge the sub-branch on the feature-master branch.
  - Commit first all **.gitignore** file before commit the rest of the code when you create a new package or new project.

## Rust
### Version and Environment
  - Rust **Compiler** : rustc 1.49.0
  - Rust **Toolchain** : rustup 1.23.1
  - Rust **package manager**: cargo 1.49.0
  - IDE : **VSCode** with extension Rust by rust-lang : *rust-lang.rust*

### Module
  >module_name

### Structure
  >MyStruct

### Variable
  - **Structure Attribut** :
    >m_varName

  - **Function Variable** : variable name must clearly identify their utility
    >varName

  - **Static Variable** :
    >varName

  - **Const Variable** :
    >VarName

  - **Enum Attribut** :
    >VarName

### Function    
  >my_function(...)

### Indentation
  - Use the **basic indentation of VSCode** or using corgo indentation by `$>cargo fmt`.

### Description
  - **Function / Class** : Use the following syntaxe
    - outer doc
      ```rust
      /// `initial` and incremented by `increment` 
      /// each time.
      pub fn new(initial: u64, increment: u64) -> Self {...}

      /**
      `initial` and incremented by `increment` each time.
      */
      pub fn new(initial: u64, increment: u64) -> Self {...}
      ```

    - inner doc

      ```rust
      //! Inner line doc
      /*!  
      - Inner block doc 
      */
      ```

  - **Comment** : Use the following syntaxe
  ```rust
  /***
    long comment
  */

  /*
    long comment
  */

  // small comment
  //// small comment
  ```
