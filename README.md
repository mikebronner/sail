# Laravel Sail Development Image

## Content
- Ubuntu 22.04, with packages:
	- Nala (modern apt replacement)
	- ZSH
	- Nano
- PHP:
	- 8.2
	- 8.3
- PHP Extensions:
	- Imagick
	- PCov
	- XDebug
- customized ZSH, with plugins:
	- git
	- zsh-artisan
	- zsh-autosuggestions
	- zsh-you-should-use
	- zsh-syntax-highlighting
	- zsh-completions
- customized P10K command prompt
- Passwordless sudo

## Uses
Perfect for development in:
- GitHub Codespaces
- Laravel Sail

## Installation
1. Update composer to allow pulling of the sail image from GitHub:
  ```
  tba
  ```
2. Update your `docker-compose.yml` image reference to (replace `<x.y>` with your desired version):
  ```yml
  laravel.test:
    image: ghcr.io/mikebronner/sail/php-<x.y>:latest
  ```
