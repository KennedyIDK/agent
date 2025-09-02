# Agent

A simple wrapper around the [age](https://age-encryption.org/) encryption tool. It provides a user-friendly interface for both key-based and password-based encryption, with automatic file naming and optional file removal.

The script is primarily intended to be used in the terminal, but can also be used non-interactively, for example, as a custom action in a file manager.

Output files are named the same as the input files, with the `.age` extension added for encryption, and the extension removed for decryption.

## Usage

```bash
agent [options] <input_files>
```

### Options

You can change the default behaviour using the global variables near the top of the script.

| Option   | Description                                          |
|:--------:|------------------------------------------------------|
| `-d`     | Decrypt mode (default is encrypt)                    |
| `-p`     | Use password-based encryption (default is key-based) |
| `-r`     | Auto remove original file after encryption *          |
| `-q`     | Quiet mode (no output to terminal)                   |
| `-h`     | Show help message                                    |

\* You will be prompted whether to remove the original file when running interactively, unless the `-r` or `-q` flags were specified.

## Requirements

The [age](https://age-encryption.org/) encryption tool must be installed and available in your PATH.

## Configuration

The script uses environment variables for key-based encryption. You need to set these for key-based operations:

| Variable | Description | Required For |
|----------|-------------|--------------|
| `AGE_PUBKEY` | Your age public key | Encryption |
| `AGE_SECKEY` | Your age private key | Decryption |

I recommend setting these in your shell profile (e.g. `~/.bashrc`), just remember to keep your private key secure!

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE.md) file for details.

## Acknowledgments

- [age](https://age-encryption.org/) - The underlying encryption tool
- [FiloSottile](https://github.com/FiloSottile) - Creator of age
