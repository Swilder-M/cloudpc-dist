# cloudpc-dist

CMCC Cloud Computer Keepalive Tool

Protocol analysis: <https://codming.com/posts/cmcc-cloud-computer-keepalive/>

## Download

| Platform | Architecture | File |
|----------|-------------|------|
| macOS | Intel | `cloudpc-darwin-amd64` |
| macOS | Apple Silicon | `cloudpc-darwin-arm64` |
| Windows | x86_64 | `cloudpc-windows-amd64.exe` |
| Linux | x86_64 | `cloudpc-linux-amd64` |
| Linux | ARM64 | `cloudpc-linux-arm64` |
| Linux | ARMv7 (32-bit) | `cloudpc-linux-armv7` |
| Linux | x86 (32-bit) | `cloudpc-linux-386` |
| Linux | MIPS | `cloudpc-linux-mips` |
| Linux | MIPS LE | `cloudpc-linux-mipsle` |

## Usage

### 1. Login

```bash
./cloudpc login
```

Interactive flow: generate device ID -> input phone number -> receive SMS code -> login -> get cloud PC info. Config saved to `cloud_pc.json`.

### 2. Keepalive

```bash
# Hold connection for 120 seconds (default)
./cloudpc keepalive

# Custom duration
./cloudpc keepalive --duration 60
```

### 3. Crontab

```bash
crontab -e
```

```cron
*/10 * * * * cd /path/to/cloudpc && ./cloudpc keepalive --duration 120 >> keepalive.log 2>&1
```
