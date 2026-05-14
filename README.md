# HAVNC - Home Assistant Dashboard through VNC

A standalone Docker container that allows you to view and interact with a Home Assistant dashboard (or any other webpage) through a modern Chromium instance inside a noVNC webpage.

Very useful for devices where your browser doesn't support all the modern web features but is capable of running noVNC client - for example, older iPads or tablets.

## Quick Start

1. Clone this repository:
   ```bash
   git clone <repository-url>
   cd havnc
   ```

2. Copy the environment example file:
   ```bash
   cp .env.example .env
   ```

3. Configure your options in `config/options.json`:
   ```json
   {
     "url": "http://your-homeassistant:8123",
     "resolution": "768x1024",
     "password": null
   }
   ```

4. Start the container:
   ```bash
   docker-compose up -d
   ```

5. Access noVNC at `http://localhost:8080`

## Configuration

### Environment Variables (`.env`)

| Variable | Default | Description |
|----------|---------|-------------|
| `TZ` | `UTC` | Timezone (e.g., `America/New_York`, `Europe/London`) |
| `NOVNC_PORT` | `8080` | Port for noVNC access |

### Options (`config/options.json`)

| Option | Default | Description |
|--------|---------|-------------|
| `url` | `http://homeassistant:8123` | Target URL to display |
| `resolution` | `768x1024` | Virtual display resolution (WxH) |
| `password` | `null` | VNC password (optional, set for remote access) |

## Tips

- [Kiosk-mode](https://github.com/NemesisRE/kiosk-mode) is really useful for a cleaner look.
- [ha-lcars](https://github.com/th3jesta/ha-lcars) for the one true interface (as seen in my example photo).

## License

See LICENSE.md for details.
