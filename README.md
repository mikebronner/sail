# Laravel Sail Development Image

## Content
- Ubuntu 22.04, with packages:
	- Nala (modern apt replacement)
	- ZSH
	- Nano
- PHP:
	- 8.2
	- 8.3 (some php extensions are not fully ready, including the ones listed below)
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
Perfect for:
- GitHub Codespaces
- Laravel Sail

## Installation
1. Update composer to allow pulling of the sail image from GitHub:
  ```
  tba
  ```
2. Update your `docker-compose.yml` image reference to:
  ```yml
  laravel.test:
    image: ghcr.io/mikebronner/sail/php-8.2:latest
  ```
