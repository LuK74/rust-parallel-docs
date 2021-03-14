[Back](README.md)

# Table of Contents
1. [Technological Watch of projects in Rust](#Technological-Watch-of-projects-in-Rust)
2. [Technological Watch about our GNU Parallel Rust project](#Technological-Watch-about-our-GNU-Parallel-Rust-project)
3. [Stay informed](#To-stay-informed-about-Rust)

![trust-rust](images/illustrations/trust-rust.jpg)
---

# Technological Watch of projects in Rust

*edit : 22/02/2021*

## Origin
<!-- sources -->
[orn1]: https://fr.wikipedia.org/wiki/Rust_(langage)#Histoire
[orn2]: https://bioinfo-fr.net/rust-un-heros-au-secours-de-la-bio-informatique#:~:text=Les%20origines,qu'il%20va%20nommer%20Rust.&text=Ils%20d%C3%A9cid%C3%A8rent%20donc%20d'utiliser,:%20rapidit%C3%A9,%20concurrence%20et%20s%C3%A9curit%C3%A9.
<!--  -->

The Rust language was born from a personal project of Graydon Hoare, a developer at Mozilla, in 2006. Mozilla began to take an interest in the project in 2009 and will reawaken its work in 2010 with the launch of its Servo project, a new HTML rendering engine for the Firefox browser. 

In 2010, the project moved from the initial compiler written in OCaml to a self-hosted compiler (which can compile its own source code via a toolchain) written in Rust. This compiler is called `rustc`.

The first stable version of Rust appears in 2015.

*( source : [wikipedia][orn1], [bioinfo-fr][orn2] )*

## Foundation
<!-- sources -->
[fd1]: https://foundation.rust-lang.org "Rust Foundation Website"
[fd2]: https://www.lemagit.fr/actualites/252488003/Open-Source-Rust-aura-bientot-le-droit-a-sa-propre-fondation
[fd3]: https://rust.developpez.com/actu/312489/Microsoft-Google-AWS-Huawei-et-Mozilla-s-associent-pour-creer-la-Fondation-Rust-une-organisation-a-but-non-lucratif-chargee-de-gerer-le-langage-de-programmation/
[fd4]: https://www.silicon.fr/fondation-rust-envol-361459.html#
[fd5]: https://rust.developpez.com/actu/308193/L-equipe-Rust-annonce-la-creation-d-une-fondation-pour-le-langage-de-programmation-avant-la-fin-de-l-annee-l-assistance-de-Mozilla-sur-les-plans-legaux-et-financiers-n-etant-plus-suffisante/
<!--  -->

Mozilla specifies that the creation of the foundation aims to host the infrastructure, to support the community and above all to manage the language for the benefit of all, by making available the necessary legal, financial, technical and human resources.

The members of the foundation are Microsoft, Google, AWS, Huawei and Mozilla.

*( source : [Rust foundation][fd1] , [lemagit][fd2], [silicon][fd4], [developpez - 1][fd3], [developpez - 2][fd5] )*

## Projects
<!-- sources -->
[pj1]: https://arewegameyet.rs/
[pj2]: https://www.lemondeinformatique.fr/actualites/lire-le-runtime-tokio-rust-atteint-le-statut-10-81740.html
[pj3]: https://www.dunebook.com/amazing-rust-opensource-projects/
[pj4]: https://medium.com/digitalfrontiers/gui-programming-with-rust-c71fe4051b1a
[pj5]: https://dev.to/davidedelpapa/rust-gui-introduction-a-k-a-the-state-of-rust-gui-libraries-as-of-january-2021-40gl
[pj6]: https://serokell.io/blog/open-source-rust
[pj7]: https://project-awesome.org/rust-unofficial/awesome-rust
<!--  -->
There are today a large number of projects in Rust for :
- video game : [arewegameyet][pj1], [serokell](https://serokell.io/blog/open-source-rust#game-development)
- runtime asynchrone : [lemondeinformatique][pj2]
- GUI programming : [dev][pj5], [medium][pj4], [serokell](https://serokell.io/blog/open-source-rust#gui-development)
- Web development : [serokell](https://serokell.io/blog/open-source-rust#web-development-frameworks-for-rust)
- Blockchain : [serokell](https://serokell.io/blog/open-source-rust#blockchain)


Non-exhaustive list of projects : [dunebook][pj3], [serokell][pj6], [project-awesome][pj7]

## Operating System
<!-- sources -->
[os1]: https://www.redox-os.org/ "RedoxOS Website"
[os2]: https://rust.developpez.com/actu/301923/Microsoft-annonce-Rust-WinRT-une-projection-du-langage-Rust-pour-les-API-Windows-Runtime-implementee-comme-une-bibliotheque-basee-sur-des-fichiers-d-en-tete/
[os3]: https://windows.developpez.com/actu/311913/Microsoft-unifie-toutes-les-API-Windows-sous-une-seule-bibliotheque-Rust-generee-a-partir-de-metadonnees/
[os4]: https://serokell.io/blog/open-source-rust#operating-systems

The GNU/Linux kernel has been rewritten in Rust and is used by the operating system [RedoxOS][os1].

(*sources : [serokell][os4])*

Rust is now also used in the Microsoft Windows operating system to address robustness, security and performance issues.

*( source : [developpez - 1][os2], [developpez - 2][os3] )*

## Other
<!-- sources -->
[oth1]: https://aws.amazon.com/fr/blogs/opensource/why-aws-loves-rust-and-how-wed-like-to-help/
[oth2]: https://www.developpez.com/actu/249515/L-equipe-de-npm-choisit-Rust-pour-gerer-les-goulots-d-etranglement-lies-au-CPU-au-detriment-de-Go-C-Cplusplus-et-Java-voici-les-raisons-de-ce-choix/
<!--  -->

Rust is also used in [AWS (Amazon Web Service)][oth1] and [npm][oth2].

---
# Technological Watch about our GNU Parallel Rust project

## Asynchronous framework
### Tokio
- Command parser enhanced by Tokio (based on the std::process::Command from Rust).   
- Command struct can be used as Jobs struct, his design correspond exactly to what we were looking to implement for Jobs.   
- Command struct also comes with stdin, stdout and stderr handling function which we'll make the output handling easier.   
- A whole set of synchronizations tools are furnished like channels (oneshot, mpsc, watch,...), Mutex and Barrier.
- The module "task" also provide what we call "asynchronous green-threads" which could be very useful for our multithreaded application.
- A lot of I/O asynchronous functionalities which allow the application to be optimized

### Mio
- A low-level I/O library focusing on non-blocking APIs and event notification for building high performance I/O apps with as little overhead as possible over the OS abstractions.   
- Provides tools to create an event loop, using a mio::Poll which monitors event::Sources, waiting until one or more become "ready" for some class of operations (read/write).
- Provides non blocking TCP/UDP.   

### Comparison between Mio & Tokio
Mio can be seen as an anterior low level version of Tokio, it has less functionalities than Tokio but is way easier to apprehend. It let the user have the tools to create a basic event loop using tcp & udp connections. It misses a lot of functionalities which could be required for the project though.
Tokio on the contrary has more features which are related to the project, but is harder to apprehend because it uses a lot of concepts we have to understand before using the tools it offers.

---
# To stay informed about Rust
<!-- sources -->
[tw0]: https://www.rust-lang.org/fr
[tw1]: https://crates.io
[tw2]: https://forge.rust-lang.org/index.html
[tw3]: https://www.reddit.com/r/rust/
<!--  -->

- [Rust Lang][tw0]
- [Rust Crates][tw1]
- [Rust Forge][tw2]
    - [Discord](https://discord.gg/rust-lang)
- [Reddit][tw3]
