# Instalación de dependencias (Raspberry Pi)

Actualizar repositorios e instalar los paquetes necesarios:

```bash
sudo apt update
sudo apt install hostapd dnsmasq mosquitto mosquitto-clients wireshark -y
```

## Detener servicios mientras se configuran

```bash
sudo systemctl stop hostapd
sudo systemctl stop dnsmasq
sudo systemctl stop mosquitto

sudo systemctl disable hostapd
sudo systemctl disable dnsmasq
```

## Verificar instalación

```bash
hostapd -v
dnsmasq --version
mosquitto -h
wireshark --version
```

## Verificar nombre de la interfaz Wi-Fi

```bash
ip addr
```

o

```bash
iw dev
```

## Habilitar y reiniciar servicios

Una vez creados los archivos de configuración:

```bash
sudo systemctl enable hostapd
sudo systemctl enable dnsmasq
sudo systemctl enable mosquitto

sudo systemctl restart hostapd
sudo systemctl restart dnsmasq
sudo systemctl restart mosquitto
```

## Verificar estado de los servicios

```bash
sudo systemctl status hostapd
sudo systemctl status dnsmasq
sudo systemctl status mosquitto
```

## Ver logs

### hostapd

```bash
journalctl -u hostapd -f
```

### dnsmasq

```bash
journalctl -u dnsmasq -f
```

### mosquitto

```bash
journalctl -u mosquitto -f
```