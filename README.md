# Secure Password Generator

## Description

This simple docker web application is designed to generate secure passwords or passphrases with customizable options. Users can opt to generate either a random password with specific criteria or a passphrase composed of random words. It includes features for enhancing password strength, such as including uppercase letters, digits, and special characters for passwords, or capitalizing words and specifying separators for passphrases.

A demo of the software is available on [https://pwgen.joonatanh.com](https://pwgen.joonatanh.com) (`main` branch).

## Features

- **Progressive Web Application (PWA)**
- **Password Generation**: Generate a random password with options to include:
  - Uppercase letters
  - Digits
  - Special characters
- **Passphrase Generation**: Generate a passphrase with options to:
  - Capitalize the first letter of each word
  - Choose a separator between words (space, random number, random special character, or a user-defined character)
  - Option to add either numbers or special characters after the words
  - Set the maximum word length
  - Use either English or Finnish word list
- **User Interface**: Display the generated password or passphrase in a user-friendly interface with the option to copy it to the clipboard.
- **Security Check**: Check all generated passwords and passphrases against the haveibeenpwned database using their API to ensure users are not shown a compromised password.
- **Offline Mode**: Added a feature to disable checking passwords against the haveibeenpwned API, suitable for instances running in isolated networks or where external API access is unnecessary.

## How to Use

1. **Install Docker** if you haven't already.
2. **Run the Generator**: Pull the image `jocxfin/pwgen:latest` and then run it using the following commands:

```bash
docker pull jocxfin/pwgen:latest
docker run -d -p 5069:5069 jocxfin/pwgen:latest
```

To enable **Offline Mode**, append `-e NO_API_CHECK=true` to the `docker run` command:

```bash
docker run -d -p 5069:5069 -e NO_API_CHECK=true jocxfin/pwgen:latest
```

## Requirements

- Docker
- Any modern web browser

## License

This project is open-source and available under the AGPL-3.0 license.
