# Terratarget

Terratarget is a Python script designed to enhance Terraform's targeting functionality, allowing for more dynamic and flexible targeting of resources through regex patterns. This tool wraps Terraform commands, adding support for regex patterns in the `-target` option.

## Features

- **Regex Support**: Allows using regex patterns with the `-target` option to match resources dynamically.
- **Exclusion Support**: Allows using regex patterns with the `-except` option to exclude specific resources from being targeted.
- **Confirmation Prompt**: Provides a confirmation prompt before executing Terraform commands, enhancing safety (can be bypassed with `-auto-approve` for `apply`).
- **Versatile**: Supports both `terraform plan` and `terraform apply` commands.

## Prerequisites

- Python 3.x
- Terraform

Ensure both Python and Terraform are installed on your system and accessible from your command line.

## Installation

1. Clone this repository or download `terratarget` directly.
2. Make the script executable: `chmod +x terratarget`

## Usage

Basic usage follows Terraform's syntax, with the addition of regex pattern support for the `-target` and `-except` options:

```
./terratarget plan -target="resource_type.resource_name_pattern*"
./terratarget apply -target="resource_type.resource_name_pattern*" -auto-approve
./terratarget plan -target="resource_type.resource_name_pattern*" -except="excluded_pattern"
```

### Examples

- Plan changes only for resources matching a specific pattern:

```
./terratarget plan -target="aws_instance.example*"
```

- Apply changes with auto-approval for matched resources:

```
./terratarget apply -target="google_dns_record_set.www_tld.*" -auto-approve
```

- Plan changes for resources matching a specific pattern, but exclude certain resources:

```
./terratarget plan -target="google_dns_record_set.core-ilb-us.*" -except=".*test.*"
```

## Contributing

Contributions are welcome! If you have suggestions for improvements or bug fixes, please feel free to submit a pull request or open an issue.

## License

Distributed under the MIT License. See `LICENSE` for more information.
