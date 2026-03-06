# QR Code Generator

A professional, containerized Python utility to generate high-quality, customized QR codes instantly. This project is built with security best practices, including non-root Docker execution and automated build checks.

## Features
* **Customizable:** Change URL, fill color, and background color via environment variables or CLI.
* **Docker Ready:** Fully containerized with a slim, secure image.
* **Automated:** Includes GitHub Actions for build verification.
* **Persistence:** Automatically saves QR codes to a local directory using Docker volumes.

---

## Quick Start (Docker Compose)
The easiest way to run this tool is using Docker Compose.

1. **Clone the repository:**
```bash
   git clone https://github.com/Aniket-NJIT/qr-code-generator
   cd qr-code-generator
```
2. **Run the Generator:**
```bash
    docker compose up
```
Your QR code will appear in the ./qr_codes folder on your computer.

---

## Running via Docker Hub
If you don't want to download the source code, you can pull and run the image directly from Docker Hub:
```bash
docker run --rm -v "$(pwd)/qr_codes:/app/qr_codes" akhalate/qr-code-generator-app --url "[https://google.com](https://google.com)"
```

---

## Configuration (Environment Variables)
You can customize the output by editing the `docker-compose.yml` file or passing environment variables:
- FILL_COLOR - Default red. The color of the QR code modules.
- BACK_COLOR - Default white. The background color of the image.
- QR_CODE_DIR - Default	qr_codes. The internal directory for saving files

---

## Local Development
If you prefer to run the script natively:
1. Install dependencies:
```bash
    pip install -r requirements.txt
```

2. Run the script:
```bash
    python main.py --url "https://yourlink.com"
```
---

## CI/CD
This project uses GitHub Actions to verify that the Docker image builds successfully on every push to the main branch. This ensures the project remains stable and usable for the community.