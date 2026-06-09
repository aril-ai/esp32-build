# ESP32-S3 N16R8 NAT Router - Optimized Build

## Cara Build

1. Upload semua isi folder ini ke repo GitHub baru kamu
2. Buka tab **Actions** di repo
3. Klik **"Build ESP32-S3 N16R8 NAT Router (Optimized)"**
4. Klik **"Run workflow"** → **"Run workflow"**
5. Tunggu ~10 menit
6. Download artifact **esp32s3-n16r8-optimized**

## Cara Flash

```bash
cd esp32s3-n16r8-optimized

python3 -m esptool \
  --chip esp32s3 \
  --port /dev/ttyUSB0 \
  --baud 460800 \
  write-flash \
  --flash-mode dio \
  --flash-freq 80m \
  --flash-size 16MB \
  0x0     bootloader.bin \
  0x8000  partition-table.bin \
  0xe000  ota_data_initial.bin \
  0x10000 esp32_nat_router.bin
```
