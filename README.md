import socket

def scan_ports(target, ports):
    print(f"Scanning {target}...")
    for port in ports:
        try:
            sock = socket.socket()
            sock.settimeout(0.5)
            sock.connect((target, port))
            print(f"[+] Port {port} is OPEN")
        except:
            pass
        finally:
            sock.close()

if __name__ == "__main__":
    target_ip = input("Target IP: ")
    ports = range(1, 1025)
    scan_ports(target_ip, ports)
