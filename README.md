#!/bin/bash
echo "Enter target IP:"
read target

echo "Scanning ports on $target..."

for port in {20..1024}; do
  (echo >/dev/tcp/$target/$port) >/dev/null 2>&1 && echo "Port $port is open"
done
