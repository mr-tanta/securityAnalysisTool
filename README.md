# Vulnerability Scanning Tool
### By Abraham Esandayinze Tanta

The Vulnerability Scanning Tool is a Python script that allows you to perform vulnerability scans on single or multiple
targets. It leverages the Nmap tool to scan for open ports and uses the Vulners script for vulnerability detection. The
tool generates a PDF report of the scan results and optionally sends it via email using SendGrid.

## Prerequisites

- Python 3.x
- Nmap (Make sure it is installed and available in the system's PATH)
- SendGrid API key (if using email functionality)

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/your-username/vulnerability-scanning-tool.git
   ```
2. Navigate to the project directory:
   ```bash
   cd vulnerability-scanning-tool
   ```

3. Install the required Python packages:
   ```bash
      pip install -r requirements.txt
      ```
4. Create a SendGrid account and generate an API key. See [here](https://sendgrid.com/docs/ui/account-and-settings/api-keys/) for instructions. (Optional)

## Usage


The tool can be used to scan a single target or multiple targets from a file.

### Single Target Scan
To perform a vulnerability scan on a single target, use the following command:

   ```bash  
   python main.py -t <IP_or_URL_to_scan> [-k <SendGrid_API_key>] [-s <sender_email>] [-r <recipient_email>]
   ```

- `<IP_or_URL_to_scan>`: The IP address or URL of the target to scan.
- `<SendGrid_API_key>`: The SendGrid API key to use for sending the report via email. (Optional)
- `<sender_email>`: The email address of the sender. (Optional)
- `<recipient_email>`: The email address of the recipient. (Optional)

### Multiple Targets Scan
To perform a vulnerability scan on multiple targets from a file, create a file named target.txt and add each target IP
address or URL on a separate line. Then, use the following command:

   ```bash
   python main.py -f target.txt [-k <SendGrid_API_key>] [-s <sender_email>] [-r <recipient_email>]
   ```

- `-f, --target-file <path_to_target.txt>:` Path to the target.txt file containing the list of targets.
- `<SendGrid_API_key>`: The SendGrid API key to use for sending the report via email. (Optional)
- `<sender_email>`: The email address of the sender. (Optional)
- `<recipient_email>`: The email address of the recipient. (Optional)

## Example

Here's an example command to perform a vulnerability scan on a single target and send the results via email:

```bash
python main.py -t example.com -k <SendGrid_API_key> -s sender@example.com -r recipient@example.com
```

## License

This project is licensed under the MIT License 

Feel free to customize the contents of the `README.md` file based on your specific project and requirements. Include any
additional information or instructions that would be helpful for users of the vulnerability scanning tool.
