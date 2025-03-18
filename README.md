# 🚩 Pwn-Host - Pwn Challenge Hosting for CTF

![Docker](https://img.shields.io/badge/Docker-✓-blue?logo=docker)
![CTF](https://img.shields.io/badge/CTF_Ready-✓-red)
![Security](https://img.shields.io/badge/Secure_Chroot-✓-green)

Secure Docker container setup for hosting CTF pwn challenges with auto-configuration. Features resource limits, chroot isolation, and 32-bit binary support. Perfect for organizers needing reliable challenge deployment. 

### Installation
```bash
git clone https://github.com/your-username/Pwn-Host.git
cd Pwn-Host
```

## Usage

### Hosting a Challenge
1. **Prepare Challenge Files**
   ```bash
   # Save the Binary file in files/vuln and named as "vuln"
   
   # Add your flag
   echo "FLAG{test_flag}" > files/flag.txt
   ```

2. **Deploy Container**
   ```bash
   ./start.sh chall 1337
   ```

3. **Connect Players**
   ```bash
   nc 127.0.0.1 1337
   ```
   

## 🛠 Troubleshooting

### Common Issues
**Missing Libraries**
```bash
# Check dependencies
docker exec -it <container> ldd /home/ctf/vuln

# Rebuild with debug
docker build --no-cache -t debug-image .
```

**Connection Issues**
```bash
# Check container logs
docker logs <container>

# Verify port mapping
docker port <container>
```

