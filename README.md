<!-- Improved compatibility of back to top link: See: https://github.com/othneildrew/Best-README-Template/pull/73 -->

<a name="readme-top"></a>

<!--
*** Thanks for checking out the Best-README-Template. If you have a suggestion
*** that would make this better, please fork the repo and create a pull request
*** or simply open an issue with the tag "enhancement".
*** Don't forget to give the project a star!
*** Thanks again! Now go create something AMAZING! :D
-->

<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->

[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![GNU License][license-shield]][license-url]

<br />
<div align="center">

<h3 align="center">Thaumiel Server</h3>

  <p align="center">
    A set of configs to automate standing up a minecraft server with the Thaumiel modpack(s).
    <br />
    <a href="https://github.com/thaumiel-modpacks/thaumiel-server"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/thaumiel-modpacks/thaumiel-server/issues">Report Bug</a>
    ·
    <a href="https://github.com/thaumiel-modpacks/thaumiel-server/issues">Request Feature</a>
  </p>
</div>

<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>

<!--toc:start-->
- [About The Project](#about-the-project)
  - [Built With](#built-with)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Setup](#setup)
- [Usage](#usage)
- [Roadmap](#roadmap)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)
- [Acknowledgments](#acknowledgments)
<!--toc:end-->


  </details>

<!-- ABOUT THE PROJECT -->

## About The Project

This repository houses everything you need to stand up a Thaumiel modpack minecraft server, complete with automated backups, subdomain routing, etc. Currently, it supports running a single server running the Thaumiel 23 modpack, however it is likely to be extended to house multiple simultaneous servers.

### Built With

- [![Docker][Docker]][Docker-url]
- [![itzg/docker-minecraft-server][itzg/docker-minecraft-server]][itzg/docker-minecraft-server-url]
- [![itzg/mc-router][itzg/mc-router]][itzg/mc-router-url]
- [![itzg/docker-mc-backup][itzg/docker-mc-backup]][itzg/docker-mc-backup-url]
- [![Packwiz][Packwiz]][Packwiz-url]

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- GETTING STARTED -->

## Getting Started

This project is not designed to be run without any configuration. Please make sure you've red through the entirety of `docker-compose.yml` and referenced it against the [image documentation](https://docker-minecraft-server.readthedocs.io/en/latest/) before trying to begin.

### Prerequisites

The only real pre-requisite is Docker and Compose. This can vary from easy to somewhat complicated to get working, make sure to follow the [install instructions for Docker](https://docs.docker.com/get-docker/) carefully.

### Setup

1. Clone the repo
   ```sh
   git clone https://github.com/thaumiel-modpacks/thaumiel-server.git
   ```
2. Configure `docker-compose.yml`. Most of what you'll want to change is in the `t23` environment options.
3. Add whitelisted players to `whitelist.json` and any operators to `ops.json` using the regular minecraft formats
4. In `.env`, change the password for RCON, and then set an appropriate routing command according to the [router documentation](https://github.com/itzg/mc-router), assuming you're running your server behind a subdomain.
5. Start an individual server (you'll want to do this for every configured server):
   ```sh
   docker compose up t23
   ```
   You'll want to watch for any Packwiz failures -- it's likely one or two mods will be unavailable to the API and you'll have to download them manually. Download them and add them to the respective mods folder, in this example, `t23-data/mods` (you'll probably have to create the folder).

   If any such failures occur, you'll want to `ctrl-c` out, resolve them, and then try again.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- USAGE EXAMPLES -->

## Usage

Starting everything is simple:

```sh
docker compose up
```

If you'd prefer to do things one at a time, for instance, if there are multiple configured servers:

```sh
docker compose up router
docker compose up t23
```

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- ROADMAP -->

## Roadmap

- [ ] Additional server configs

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- CONTRIBUTING -->

## Contributing

If there's anything you think could be improved, feel free to fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- LICENSE -->

## License

Distributed under the GNU GPL v3 License. See `LICENSE.txt` for more information.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- CONTACT -->

## Contact

All contact with regard to this and other thaumiel-modpacks projects can be handled in respective repos, or by contacting the organization.

Project Link: [https://github.com/thaumiel-modpacks/thaumiel-server](https://github.com/github_username/repo_name)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- ACKNOWLEDGMENTS -->

## Acknowledgments

- [Best-README-Template](https://github.com/othneildrew/Best-README-Template) for the README template.
- [Packwiz](https://packwiz.infra.link/) for the modpack manager upon which this project is based.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->

[contributors-shield]: https://img.shields.io/github/contributors/thaumiel-modpacks/thaumiel-server.svg?style=for-the-badge
[contributors-url]: https://github.com/thaumiel-modpacks/thaumiel-server/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/thaumiel-modpacks/thaumiel-server.svg?style=for-the-badge
[forks-url]: https://github.com/thaumiel-modpacks/thaumiel-server/network/members
[stars-shield]: https://img.shields.io/github/stars/thaumiel-modpacks/thaumiel-server.svg?style=for-the-badge
[stars-url]: https://github.com/thaumiel-modpacks/thaumiel-server/stargazers
[issues-shield]: https://img.shields.io/github/issues/thaumiel-modpacks/thaumiel-server.svg?style=for-the-badge
[issues-url]: https://github.com/thaumiel-modpacks/thaumiel-server/issues
[license-shield]: https://img.shields.io/github/license/thaumiel-modpacks/thaumiel-server.svg?style=for-the-badge
[license-url]: https://github.com/thaumiel-modpacks/thaumiel-server/blob/master/LICENSE.txt
[Packwiz-url]: https://packwiz.infra.link/
[Packwiz]: https://img.shields.io/badge/Packwiz-000000?style=for-the-badge&logo=github
[Docker-url]: https://www.docker.com/
[Docker]: https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker
[itzg/docker-minecraft-server-url]: https://docker-minecraft-server.readthedocs.io/en/latest/
[itzg/docker-minecraft-server]: https://img.shields.io/badge/itzg/docker--minecraft--server-000000?style=for-the-badge&logo=github
[itzg/mc-router-url]: https://docker-minecraft-server.readthedocs.io/en/latest/
[itzg/mc-router]: https://img.shields.io/badge/itzg/mc--router-000000?style=for-the-badge&logo=github
[itzg/docker-mc-backup-url]: https://github.com/itzg/docker-mc-backup
[itzg/docker-mc-backup]: https://img.shields.io/badge/itzg/docker--mc--backup-000000?style=for-the-badge&logo=github
