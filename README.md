{
    "log": {
        "disabled": false,
        "level": "fatal",
        "timestamp": true
    },
    "experimental": {
        "clash_api": {
            "external_controller": "0.0.0.0:9090",
            "external_ui": "yacd",
            "external_ui_download_url": "https:\/\/github.com\/MetaCubeX\/Yacd-meta\/archive\/gh-pages.zip",
            "external_ui_download_detour": "direct",
            "secret": "YEBEKHE",
            "default_mode": "rule",
            "store_selected": true,
            "cache_file": "clash.db"
        }
    },
    "dns": {
        "servers": [
            {
                "address": "https:\/\/1.1.1.1\/dns-query",
                "address_resolver": "dns-direct",
                "strategy": "ipv4_only",
                "tag": "dns-remote"
            },
            {
                "address": "https:\/\/8.8.8.8\/dns-query",
                "address_resolver": "dns-local",
                "detour": "direct",
                "strategy": "ipv4_only",
                "tag": "dns-direct"
            },
            {
                "address": "local",
                "detour": "direct",
                "tag": "dns-local"
            },
            {
                "address": "rcode:\/\/success",
                "tag": "dns-block"
            }
        ],
        "rules": [
            {
                "domain_suffix": [
                    ".ir"
                ],
                "server": "dns-direct"
            },
            {
                "outbound": "direct",
                "server": "dns-direct",
                "rewrite_ttl": 20
            },
            {
                "outbound": "any",
                "server": "dns-direct",
                "rewrite_ttl": 20
            }
        ],
        "reverse_mapping": true,
        "strategy": "ipv4_only",
        "independent_cache": true
    },
    "inbounds": [
        {
            "listen": "0.0.0.0",
            "listen_port": 6450,
            "override_address": "8.8.8.8",
            "override_port": 53,
            "tag": "dns-in",
            "type": "direct"
        },
        {
            "type": "tun",
            "tag": "tun-in",
            "domain_strategy": "",
            "interface_name": "tun0",
            "inet4_address": "172.19.0.1\/30",
            "mtu": 9000,
            "auto_route": true,
            "strict_route": true,
            "stack": "system",
            "endpoint_independent_nat": true,
            "sniff": true,
            "sniff_override_destination": false
        },
        {
            "domain_strategy": "",
            "listen": "0.0.0.0",
            "listen_port": 2080,
            "sniff": true,
            "sniff_override_destination": false,
            "tag": "mixed-in",
            "type": "mixed"
        }
    ],
    "outbounds": [
        {
            "tag": "proxy",
            "type": "selector",
            "outbounds": [
                "URL-TEST",
                "@free4allVPN | US🇺🇸 | cloudconebbb.gorgorchicken.one:8443 | 31.03ms | 0️⃣1️⃣ | 1",
                "@free4allVPN | US🇺🇸 | www.69908657.xyz:443 | 45.19ms | 0️⃣2️⃣ | 2",
                "@free4allVPN | US🇺🇸 | vus5.0bad.com:443 | 73.22ms | 0️⃣3️⃣ | 3",
                "@v2ray_outlineir | US🇺🇸 | wxxjp.e5outllok.me:80 | 36.99ms | 0️⃣1️⃣ | 4",
                "@v2ray_outlineir | US🇺🇸 | V2ray.Vmesskhodam.top:8443 | 226.31ms | 0️⃣2️⃣ | 5",
                "@oneclickvpnkeys | HK🇭🇰 | 156.245.8.133:35939 | 134.37ms | 0️⃣1️⃣ | 6",
                "@oneclickvpnkeys | FR🇫🇷 | 141.94.222.208:2082 | 145.18ms | 0️⃣2️⃣ | 7",
                "@oneclickvpnkeys | FR🇫🇷 | 51.158.238.229:443 | 131.55ms | 0️⃣3️⃣ | 8",
                "@prrofile_purple | RS🇷🇸 | 37.120.193.102:52920 | 159.75ms | 0️⃣1️⃣ | 9",
                "@prrofile_purple | US🇺🇸 | V2ray.Vmesskhodam.top:8443 | 9.16ms | 0️⃣2️⃣ | 10",
                "@prrofile_purple | US🇺🇸 | 89.116.38.193:3456 | 61.22ms | 0️⃣3️⃣ | 11",
                "@azadi_az_inja_migzare | US🇺🇸 | speedtest.net:443 | 44.47ms | 0️⃣1️⃣ | 12",
                "@customv2ray | IR🇮🇷 | snapp.ir:443 | 433.98ms | 0️⃣1️⃣ | 13",
                "@customv2ray | US🇺🇸 | 45.199.138.74:36917 | 134.59ms | 0️⃣2️⃣ | 14",
                "@customv2ray | US🇺🇸 | 45.199.138.189:43560 | 134.42ms | 0️⃣3️⃣ | 15",
                "@vpn_ioss | US🇺🇸 | www.baidu.com:443 | 347.37ms | 0️⃣1️⃣ | 16",
                "@ShadowProxy66 | US🇺🇸 | rockp.blanku.me:443 | 37.77ms | 0️⃣1️⃣ | 17",
                "@hashmakvpn | DE🇩🇪 | 91.107.131.254:8443 | 142.95ms | 0️⃣1️⃣ | 18",
                "@Proxy_PJ | RELAY🚩 | sandp.blanku.me:443 | 30.93ms | 0️⃣1️⃣ | 19",
                "@Proxy_PJ | US🇺🇸 | 64.32.20.101:40039 | 8.5ms | 0️⃣2️⃣ | 20",
                "@Proxy_PJ | US🇺🇸 | 89.116.38.170:3456 | 61.68ms | 0️⃣3️⃣ | 21",
                "@vless_vmess | RELAY🚩 | V2ray.Vmesskhodam.top:8443 | 9.58ms | 0️⃣1️⃣ | 22",
                "@vless_vmess | IR🇮🇷 | sr7.vipclub.icu:2052 | 452.51ms | 0️⃣2️⃣ | 23",
                "@Cov2ray | US🇺🇸 | ro1.socifiles.com:2087 | 274.16ms | 0️⃣1️⃣ | 24",
                "@Cov2ray | US🇺🇸 | ro1.socifiles.com:2096 | 212.44ms | 0️⃣2️⃣ | 25",
                "@vpn_tehran | US🇺🇸 | 89.116.38.199:3456 | 60.11ms | 0️⃣1️⃣ | 26",
                "@vpn_tehran | RELAY🚩 | hiddis2.freelines.net:443 | 41.08ms | 0️⃣2️⃣ | 27",
                "@vpn_tehran | US🇺🇸 | ddp2.1808.cf:80 | 189.45ms | 0️⃣3️⃣ | 28",
                "@proxystore11 | US🇺🇸 | wxll.e5outllok.me:80 | 28.82ms | 0️⃣1️⃣ | 29",
                "@proxystore11 | RELAY🚩 | wxxjp.e5outllok.me:80 | 9.34ms | 0️⃣2️⃣ | 30",
                "@yaney_01 | US🇺🇸 | sg1.sanfencdn2.com:2052 | 93.78ms | 0️⃣1️⃣ | 31",
                "@fnet00 | DE🇩🇪 | 91.107.131.254:8443 | 144.97ms | 0️⃣1️⃣ | 32",
                "@v2Line | FR🇫🇷 | 141.94.222.208:2082 | 150.02ms | 0️⃣1️⃣ | 33",
                "@v2Line | GB🇬🇧 | vuk2.0bad.com:443 | 195ms | 0️⃣2️⃣ | 34",
                "@vmessiran | US🇺🇸 | 158.101.7.8:80 | 56.56ms | 0️⃣1️⃣ | 35",
                "@vmessiran | US🇺🇸 | a7.iraniancp.fun:8880 | 113.72ms | 0️⃣2️⃣ | 36",
                "@Awlix_ir | US🇺🇸 | jofdji.irancel-mokhabera-mamad-raitel-mic-irancel-hamrah-aval-server.shop:2053 | 48.39ms | 0️⃣1️⃣ | 37",
                "@Awlix_ir | RELAY🚩 | jofdji.irancel-mokhabera-mamad-raitel-mic-irancel-hamrah-aval-server.shop:2053 | 9.49ms | 0️⃣2️⃣ | 38",
                "@Awlix_ir | US🇺🇸 | jofdji.irancel-mokhabera-mamad-raitel-mic-irancel-hamrah-aval-server.shop:2053 | 9.25ms | 0️⃣3️⃣ | 39"
            ]
        },
        {
            "tag": "URL-TEST",
            "type": "urltest",
            "outbounds": [
                "@free4allVPN | US🇺🇸 | cloudconebbb.gorgorchicken.one:8443 | 31.03ms | 0️⃣1️⃣ | 1",
                "@free4allVPN | US🇺🇸 | www.69908657.xyz:443 | 45.19ms | 0️⃣2️⃣ | 2",
                "@free4allVPN | US🇺🇸 | vus5.0bad.com:443 | 73.22ms | 0️⃣3️⃣ | 3",
                "@v2ray_outlineir | US🇺🇸 | wxxjp.e5outllok.me:80 | 36.99ms | 0️⃣1️⃣ | 4",
                "@v2ray_outlineir | US🇺🇸 | V2ray.Vmesskhodam.top:8443 | 226.31ms | 0️⃣2️⃣ | 5",
                "@oneclickvpnkeys | HK🇭🇰 | 156.245.8.133:35939 | 134.37ms | 0️⃣1️⃣ | 6",
                "@oneclickvpnkeys | FR🇫🇷 | 141.94.222.208:2082 | 145.18ms | 0️⃣2️⃣ | 7",
                "@oneclickvpnkeys | FR🇫🇷 | 51.158.238.229:443 | 131.55ms | 0️⃣3️⃣ | 8",
                "@prrofile_purple | RS🇷🇸 | 37.120.193.102:52920 | 159.75ms | 0️⃣1️⃣ | 9",
                "@prrofile_purple | US🇺🇸 | V2ray.Vmesskhodam.top:8443 | 9.16ms | 0️⃣2️⃣ | 10",
                "@prrofile_purple | US🇺🇸 | 89.116.38.193:3456 | 61.22ms | 0️⃣3️⃣ | 11",
                "@azadi_az_inja_migzare | US🇺🇸 | speedtest.net:443 | 44.47ms | 0️⃣1️⃣ | 12",
                "@customv2ray | IR🇮🇷 | snapp.ir:443 | 433.98ms | 0️⃣1️⃣ | 13",
                "@customv2ray | US🇺🇸 | 45.199.138.74:36917 | 134.59ms | 0️⃣2️⃣ | 14",
                "@customv2ray | US🇺🇸 | 45.199.138.189:43560 | 134.42ms | 0️⃣3️⃣ | 15",
                "@vpn_ioss | US🇺🇸 | www.baidu.com:443 | 347.37ms | 0️⃣1️⃣ | 16",
                "@ShadowProxy66 | US🇺🇸 | rockp.blanku.me:443 | 37.77ms | 0️⃣1️⃣ | 17",
                "@hashmakvpn | DE🇩🇪 | 91.107.131.254:8443 | 142.95ms | 0️⃣1️⃣ | 18",
                "@Proxy_PJ | RELAY🚩 | sandp.blanku.me:443 | 30.93ms | 0️⃣1️⃣ | 19",
                "@Proxy_PJ | US🇺🇸 | 64.32.20.101:40039 | 8.5ms | 0️⃣2️⃣ | 20",
                "@Proxy_PJ | US🇺🇸 | 89.116.38.170:3456 | 61.68ms | 0️⃣3️⃣ | 21",
                "@vless_vmess | RELAY🚩 | V2ray.Vmesskhodam.top:8443 | 9.58ms | 0️⃣1️⃣ | 22",
                "@vless_vmess | IR🇮🇷 | sr7.vipclub.icu:2052 | 452.51ms | 0️⃣2️⃣ | 23",
                "@Cov2ray | US🇺🇸 | ro1.socifiles.com:2087 | 274.16ms | 0️⃣1️⃣ | 24",
                "@Cov2ray | US🇺🇸 | ro1.socifiles.com:2096 | 212.44ms | 0️⃣2️⃣ | 25",
                "@vpn_tehran | US🇺🇸 | 89.116.38.199:3456 | 60.11ms | 0️⃣1️⃣ | 26",
                "@vpn_tehran | RELAY🚩 | hiddis2.freelines.net:443 | 41.08ms | 0️⃣2️⃣ | 27",
                "@vpn_tehran | US🇺🇸 | ddp2.1808.cf:80 | 189.45ms | 0️⃣3️⃣ | 28",
                "@proxystore11 | US🇺🇸 | wxll.e5outllok.me:80 | 28.82ms | 0️⃣1️⃣ | 29",
                "@proxystore11 | RELAY🚩 | wxxjp.e5outllok.me:80 | 9.34ms | 0️⃣2️⃣ | 30",
                "@yaney_01 | US🇺🇸 | sg1.sanfencdn2.com:2052 | 93.78ms | 0️⃣1️⃣ | 31",
                "@fnet00 | DE🇩🇪 | 91.107.131.254:8443 | 144.97ms | 0️⃣1️⃣ | 32",
                "@v2Line | FR🇫🇷 | 141.94.222.208:2082 | 150.02ms | 0️⃣1️⃣ | 33",
                "@v2Line | GB🇬🇧 | vuk2.0bad.com:443 | 195ms | 0️⃣2️⃣ | 34",
                "@vmessiran | US🇺🇸 | 158.101.7.8:80 | 56.56ms | 0️⃣1️⃣ | 35",
                "@vmessiran | US🇺🇸 | a7.iraniancp.fun:8880 | 113.72ms | 0️⃣2️⃣ | 36",
                "@Awlix_ir | US🇺🇸 | jofdji.irancel-mokhabera-mamad-raitel-mic-irancel-hamrah-aval-server.shop:2053 | 48.39ms | 0️⃣1️⃣ | 37",
                "@Awlix_ir | RELAY🚩 | jofdji.irancel-mokhabera-mamad-raitel-mic-irancel-hamrah-aval-server.shop:2053 | 9.49ms | 0️⃣2️⃣ | 38",
                "@Awlix_ir | US🇺🇸 | jofdji.irancel-mokhabera-mamad-raitel-mic-irancel-hamrah-aval-server.shop:2053 | 9.25ms | 0️⃣3️⃣ | 39"
            ],
            "url": "https:\/\/www.gstatic.com\/generate_204",
            "interval": "3m",
            "tolerance": 50
        },
        {
            "tag": "@free4allVPN | US🇺🇸 | cloudconebbb.gorgorchicken.one:8443 | 31.03ms | 0️⃣1️⃣ | 1",
            "type": "vmess",
            "server": "cloudconebbb.gorgorchicken.one",
            "server_port": 8443,
            "uuid": "aa0c4744-9568-4bee-a08b-73668a9b2a42",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            },
            "tls": {
                "enabled": true,
                "server_name": "cloudconebbb.gorgorchicken.one",
                "insecure": true,
                "disable_sni": false,
                "utls": {
                    "enabled": true,
                    "fingerprint": "chrome"
                }
            },
            "transport": {
                "type": "ws",
                "path": "\/\/cloudconebbb",
                "headers": {
                    "Host": "cloudconebbb.gorgorchicken.one"
                },
                "max_early_data": 0,
                "early_data_header_name": "Sec-WebSocket-Protocol"
            }
        },
        {
            "tag": "@free4allVPN | US🇺🇸 | www.69908657.xyz:443 | 45.19ms | 0️⃣2️⃣ | 2",
            "type": "vmess",
            "server": "69.25.115.162",
            "server_port": 443,
            "uuid": "418048af-a293-4b99-9b0c-98ca3580dd24",
            "security": "auto",
            "alter_id": 64,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            },
            "tls": {
                "enabled": true,
                "server_name": "www.69908657.xyz",
                "insecure": true,
                "disable_sni": false,
                "utls": {
                    "enabled": true,
                    "fingerprint": "chrome"
                }
            },
            "transport": {
                "type": "ws",
                "path": "\/\/path\/1688983782619",
                "headers": {
                    "Host": "www.69908657.xyz"
                },
                "max_early_data": 0,
                "early_data_header_name": "Sec-WebSocket-Protocol"
            }
        },
        {
            "tag": "@free4allVPN | US🇺🇸 | vus5.0bad.com:443 | 73.22ms | 0️⃣3️⃣ | 3",
            "type": "vmess",
            "server": "vus5.0bad.com",
            "server_port": 443,
            "uuid": "927094d3-d678-4763-8591-e240d0bcae87",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            },
            "tls": {
                "enabled": true,
                "server_name": "vus5.0bad.com",
                "insecure": true,
                "disable_sni": false,
                "utls": {
                    "enabled": true,
                    "fingerprint": "chrome"
                }
            },
            "transport": {
                "type": "ws",
                "path": "\/\/chat",
                "headers": {
                    "Host": "vus5.0bad.com"
                },
                "max_early_data": 0,
                "early_data_header_name": "Sec-WebSocket-Protocol"
            }
        },
        {
            "tag": "@v2ray_outlineir | US🇺🇸 | wxxjp.e5outllok.me:80 | 36.99ms | 0️⃣1️⃣ | 4",
            "type": "vmess",
            "server": "65.70.45.15",
            "server_port": 80,
            "uuid": "6411e9ff-8ea9-4996-803c-e32543fd3999",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            },
            "transport": {
                "type": "ws",
                "path": "\/\/",
                "headers": {
                    "Host": "wxxjp.e5outllok.me"
                },
                "max_early_data": 0,
                "early_data_header_name": "Sec-WebSocket-Protocol"
            }
        },
        {
            "tag": "@v2ray_outlineir | US🇺🇸 | V2ray.Vmesskhodam.top:8443 | 226.31ms | 0️⃣2️⃣ | 5",
            "type": "vmess",
            "server": "65.80.24.24",
            "server_port": 8443,
            "uuid": "27f06911-1a2d-449d-bef5-20d3251fb99f",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            },
            "tls": {
                "enabled": true,
                "server_name": "V2ray.Vmesskhodam.top",
                "insecure": true,
                "disable_sni": false,
                "utls": {
                    "enabled": true,
                    "fingerprint": "chrome"
                }
            },
            "transport": {
                "type": "ws",
                "path": "\/\/",
                "headers": {
                    "Host": "V2ray.Vmesskhodam.top"
                },
                "max_early_data": 0,
                "early_data_header_name": "Sec-WebSocket-Protocol"
            }
        },
        {
            "tag": "@oneclickvpnkeys | HK🇭🇰 | 156.245.8.133:35939 | 134.37ms | 0️⃣1️⃣ | 6",
            "type": "vmess",
            "server": "156.245.8.133",
            "server_port": 35939,
            "uuid": "bd249e37-7359-41ee-84a7-09e49e0ec5c4",
            "security": "auto",
            "alter_id": 64,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            }
        },
        {
            "tag": "@oneclickvpnkeys | FR🇫🇷 | 141.94.222.208:2082 | 145.18ms | 0️⃣2️⃣ | 7",
            "type": "vmess",
            "server": "141.94.222.208",
            "server_port": 2082,
            "uuid": "a79e03ad-84a7-41f6-bce9-e4c53180c507",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            },
            "transport": {
                "type": "ws",
                "path": "\/\/vmess",
                "headers": {
                    "Host": "141.94.222.208"
                },
                "max_early_data": 0,
                "early_data_header_name": "Sec-WebSocket-Protocol"
            }
        },
        {
            "tag": "@oneclickvpnkeys | FR🇫🇷 | 51.158.238.229:443 | 131.55ms | 0️⃣3️⃣ | 8",
            "type": "vmess",
            "server": "51.158.238.229",
            "server_port": 443,
            "uuid": "b060a4e1-22b7-4e0f-91fb-93496a1881ae",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            },
            "tls": {
                "enabled": true,
                "server_name": "51.158.238.229",
                "insecure": true,
                "disable_sni": false,
                "utls": {
                    "enabled": true,
                    "fingerprint": "chrome"
                }
            }
        },
        {
            "tag": "@prrofile_purple | RS🇷🇸 | 37.120.193.102:52920 | 159.75ms | 0️⃣1️⃣ | 9",
            "type": "vmess",
            "server": "37.120.193.102",
            "server_port": 52920,
            "uuid": "57170ff0-7180-4664-8f61-8debdda345f7",
            "security": "auto",
            "alter_id": 64,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            }
        },
        {
            "tag": "@prrofile_purple | US🇺🇸 | V2ray.Vmesskhodam.top:8443 | 9.16ms | 0️⃣2️⃣ | 10",
            "type": "vmess",
            "server": "vmesskhodammci1.ddns.net",
            "server_port": 8443,
            "uuid": "27f06911-1a2d-449d-bef5-20d3251fb99f",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            },
            "tls": {
                "enabled": true,
                "server_name": "V2ray.Vmesskhodam.top",
                "insecure": true,
                "disable_sni": false,
                "utls": {
                    "enabled": true,
                    "fingerprint": "chrome"
                }
            },
            "transport": {
                "type": "ws",
                "path": "\/\/",
                "headers": {
                    "Host": "V2ray.Vmesskhodam.top"
                },
                "max_early_data": 0,
                "early_data_header_name": "Sec-WebSocket-Protocol"
            }
        },
        {
            "tag": "@prrofile_purple | US🇺🇸 | 89.116.38.193:3456 | 61.22ms | 0️⃣3️⃣ | 11",
            "type": "vmess",
            "server": "89.116.38.193",
            "server_port": 3456,
            "uuid": "32e49539-f569-403d-b4b6-a8978c040d5d",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            }
        },
        {
            "tag": "@azadi_az_inja_migzare | US🇺🇸 | speedtest.net:443 | 44.47ms | 0️⃣1️⃣ | 12",
            "type": "vmess",
            "server": "2a01:4f8:c010:64bb::1",
            "server_port": 443,
            "uuid": "d5eea30f-9046-429d-9fa2-17fec71985e6",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            },
            "tls": {
                "enabled": true,
                "server_name": "2a01:4f8:c010:64bb::1",
                "insecure": true,
                "disable_sni": false,
                "utls": {
                    "enabled": true,
                    "fingerprint": "chrome"
                }
            }
        },
        {
            "tag": "@customv2ray | IR🇮🇷 | snapp.ir:443 | 433.98ms | 0️⃣1️⃣ | 13",
            "type": "vmess",
            "server": "arvancloud.ir",
            "server_port": 443,
            "uuid": "181e54dc-0a5f-4d36-8f29-0b12a07ef407",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            },
            "tls": {
                "enabled": true,
                "server_name": "snapp.ir",
                "insecure": true,
                "disable_sni": false,
                "utls": {
                    "enabled": true,
                    "fingerprint": "chrome"
                }
            },
            "transport": {
                "type": "ws",
                "path": "\/\/downloader\/8080",
                "headers": {
                    "Host": "test1.jamshidmendez.ir"
                },
                "max_early_data": 0,
                "early_data_header_name": "Sec-WebSocket-Protocol"
            }
        },
        {
            "tag": "@customv2ray | US🇺🇸 | 45.199.138.74:36917 | 134.59ms | 0️⃣2️⃣ | 14",
            "type": "vmess",
            "server": "45.199.138.74",
            "server_port": 36917,
            "uuid": "6fa560d4-35c5-4968-adfc-812c52878b84",
            "security": "auto",
            "alter_id": 64,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            }
        },
        {
            "tag": "@customv2ray | US🇺🇸 | 45.199.138.189:43560 | 134.42ms | 0️⃣3️⃣ | 15",
            "type": "vmess",
            "server": "45.199.138.189",
            "server_port": 43560,
            "uuid": "418048af-a293-4b99-9b0c-98ca3580dd24",
            "security": "auto",
            "alter_id": 64,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            }
        },
        {
            "tag": "@vpn_ioss | US🇺🇸 | www.baidu.com:443 | 347.37ms | 0️⃣1️⃣ | 16",
            "type": "vmess",
            "server": "135.125.135.63",
            "server_port": 443,
            "uuid": "2ebed3b4-de9b-437c-a962-5ce12523b0f0",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            },
            "tls": {
                "enabled": true,
                "server_name": "135.125.135.63",
                "insecure": true,
                "disable_sni": false,
                "utls": {
                    "enabled": true,
                    "fingerprint": "chrome"
                }
            }
        },
        {
            "tag": "@ShadowProxy66 | US🇺🇸 | rockp.blanku.me:443 | 37.77ms | 0️⃣1️⃣ | 17",
            "type": "vmess",
            "server": "104.24.145.43",
            "server_port": 443,
            "uuid": "824c58b1-65ba-4680-a609-663a000dbb92",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            },
            "tls": {
                "enabled": true,
                "server_name": "rockp.blanku.me",
                "insecure": true,
                "disable_sni": false,
                "utls": {
                    "enabled": true,
                    "fingerprint": "chrome"
                }
            },
            "transport": {
                "type": "ws",
                "path": "\/\/wss13889",
                "headers": {
                    "Host": "rock.blanku.me"
                },
                "max_early_data": 0,
                "early_data_header_name": "Sec-WebSocket-Protocol"
            }
        },
        {
            "tag": "@hashmakvpn | DE🇩🇪 | 91.107.131.254:8443 | 142.95ms | 0️⃣1️⃣ | 18",
            "type": "vmess",
            "server": "91.107.131.254",
            "server_port": 8443,
            "uuid": "49e6b8ea-00a8-4a4d-c53b-b950050ef79c",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            }
        },
        {
            "tag": "@Proxy_PJ | RELAY🚩 | sandp.blanku.me:443 | 30.93ms | 0️⃣1️⃣ | 19",
            "type": "vmess",
            "server": "104.27.203.169",
            "server_port": 443,
            "uuid": "b3a21def-5fcc-47a8-a6a0-a34e29d5288a",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            },
            "tls": {
                "enabled": true,
                "server_name": "sandp.blanku.me",
                "insecure": true,
                "disable_sni": false,
                "utls": {
                    "enabled": true,
                    "fingerprint": "chrome"
                }
            },
            "transport": {
                "type": "ws",
                "path": "\/\/wss51068",
                "headers": {
                    "Host": "sand.blanku.me"
                },
                "max_early_data": 0,
                "early_data_header_name": "Sec-WebSocket-Protocol"
            }
        },
        {
            "tag": "@Proxy_PJ | US🇺🇸 | 64.32.20.101:40039 | 8.5ms | 0️⃣2️⃣ | 20",
            "type": "vmess",
            "server": "64.32.20.101",
            "server_port": 40039,
            "uuid": "c1bad9a6-1482-4941-a0c4-e85f3cbbcb5a",
            "security": "auto",
            "alter_id": 64,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            }
        },
        {
            "tag": "@Proxy_PJ | US🇺🇸 | 89.116.38.170:3456 | 61.68ms | 0️⃣3️⃣ | 21",
            "type": "vmess",
            "server": "89.116.38.170",
            "server_port": 3456,
            "uuid": "32e49539-f569-403d-b4b6-a8978c040d5d",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            }
        },
        {
            "tag": "@vless_vmess | RELAY🚩 | V2ray.Vmesskhodam.top:8443 | 9.58ms | 0️⃣1️⃣ | 22",
            "type": "vmess",
            "server": "vmesskhodammci1.ddns.net",
            "server_port": 8443,
            "uuid": "ee84c8da-5a49-4a91-9edc-03239b19d59f",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            },
            "tls": {
                "enabled": true,
                "server_name": "V2ray.Vmesskhodam.top",
                "insecure": true,
                "disable_sni": false,
                "utls": {
                    "enabled": true,
                    "fingerprint": "chrome"
                }
            },
            "transport": {
                "type": "ws",
                "path": "\/\/",
                "headers": {
                    "Host": "V2ray.Vmesskhodam.top"
                },
                "max_early_data": 0,
                "early_data_header_name": "Sec-WebSocket-Protocol"
            }
        },
        {
            "tag": "@vless_vmess | IR🇮🇷 | sr7.vipclub.icu:2052 | 452.51ms | 0️⃣2️⃣ | 23",
            "type": "vmess",
            "server": "sr7.vipclub.icu",
            "server_port": 2052,
            "uuid": "4439c68c-df2e-4276-8ebf-8ed72c0f5fa6",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            },
            "transport": {
                "type": "ws",
                "path": "\/\/",
                "headers": {
                    "Host": "sr7.vipclub.icu"
                },
                "max_early_data": 0,
                "early_data_header_name": "Sec-WebSocket-Protocol"
            }
        },
        {
            "tag": "@Cov2ray | US🇺🇸 | ro1.socifiles.com:2087 | 274.16ms | 0️⃣1️⃣ | 24",
            "type": "vmess",
            "server": "104.22.13.192",
            "server_port": 2087,
            "uuid": "525e5ec0-3a6b-11ee-ac71-1239d0255272",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            },
            "tls": {
                "enabled": true,
                "server_name": "ro1.socifiles.com",
                "insecure": true,
                "disable_sni": false,
                "utls": {
                    "enabled": true,
                    "fingerprint": "chrome"
                }
            },
            "transport": {
                "type": "grpc",
                "service_name": "vmgrpc",
                "idle_timeout": "15s",
                "ping_timeout": "15s",
                "permit_without_stream": false
            }
        },
        {
            "tag": "@Cov2ray | US🇺🇸 | ro1.socifiles.com:2096 | 212.44ms | 0️⃣2️⃣ | 25",
            "type": "vmess",
            "server": "104.31.16.65",
            "server_port": 2096,
            "uuid": "5f9080b0-3b83-11ee-abfe-1239d0255272",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            },
            "tls": {
                "enabled": true,
                "server_name": "ro1.socifiles.com",
                "insecure": true,
                "disable_sni": false,
                "utls": {
                    "enabled": true,
                    "fingerprint": "chrome"
                }
            },
            "transport": {
                "type": "grpc",
                "service_name": "vmgrpc",
                "idle_timeout": "15s",
                "ping_timeout": "15s",
                "permit_without_stream": false
            }
        },
        {
            "tag": "@vpn_tehran | US🇺🇸 | 89.116.38.199:3456 | 60.11ms | 0️⃣1️⃣ | 26",
            "type": "vmess",
            "server": "89.116.38.199",
            "server_port": 3456,
            "uuid": "32e49539-f569-403d-b4b6-a8978c040d5d",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            }
        },
        {
            "tag": "@vpn_tehran | RELAY🚩 | hiddis2.freelines.net:443 | 41.08ms | 0️⃣2️⃣ | 27",
            "type": "vmess",
            "server": "mbt.ircf.space",
            "server_port": 443,
            "uuid": "79770a32-9607-4919-9483-0f1794559390",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            },
            "tls": {
                "enabled": true,
                "server_name": "hiddis2.freelines.net",
                "insecure": true,
                "disable_sni": false,
                "utls": {
                    "enabled": true,
                    "fingerprint": "chrome"
                }
            },
            "transport": {
                "type": "ws",
                "path": "\/\/juYLyvNBpY0LBOAommy2aJE",
                "headers": {
                    "Host": "hiddis2.freelines.net"
                },
                "max_early_data": 0,
                "early_data_header_name": "Sec-WebSocket-Protocol"
            }
        },
        {
            "tag": "@vpn_tehran | US🇺🇸 | ddp2.1808.cf:80 | 189.45ms | 0️⃣3️⃣ | 28",
            "type": "vmess",
            "server": "141.101.122.233",
            "server_port": 80,
            "uuid": "4a47e680-d860-4e63-9fa6-813857fb0f42",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            },
            "transport": {
                "type": "ws",
                "path": "\/4a47e680",
                "headers": {
                    "Host": "ddp2.1808.cf"
                },
                "max_early_data": 0,
                "early_data_header_name": "Sec-WebSocket-Protocol"
            }
        },
        {
            "tag": "@proxystore11 | US🇺🇸 | wxll.e5outllok.me:80 | 28.82ms | 0️⃣1️⃣ | 29",
            "type": "vmess",
            "server": "wxll.e5outllok.me",
            "server_port": 80,
            "uuid": "edca7082-26c3-4047-9de4-2ecbeae7318e",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            },
            "transport": {
                "type": "ws",
                "path": "\/\/",
                "headers": {
                    "Host": "wxll.e5outllok.me"
                },
                "max_early_data": 0,
                "early_data_header_name": "Sec-WebSocket-Protocol"
            }
        },
        {
            "tag": "@proxystore11 | RELAY🚩 | wxxjp.e5outllok.me:80 | 9.34ms | 0️⃣2️⃣ | 30",
            "type": "vmess",
            "server": "wxxjp.e5outllok.me",
            "server_port": 80,
            "uuid": "0a6fa33f-1a08-4d98-a7bc-0fecdeb7037b",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            },
            "transport": {
                "type": "ws",
                "path": "\/\/",
                "headers": {
                    "Host": "wxxjp.e5outllok.me"
                },
                "max_early_data": 0,
                "early_data_header_name": "Sec-WebSocket-Protocol"
            }
        },
        {
            "tag": "@yaney_01 | US🇺🇸 | sg1.sanfencdn2.com:2052 | 93.78ms | 0️⃣1️⃣ | 31",
            "type": "vmess",
            "server": "cfcdn3.sanfencdn.net",
            "server_port": 2052,
            "uuid": "502e4ff1-92e0-4a0e-be0e-3a0e36530e3e",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            },
            "transport": {
                "type": "ws",
                "path": "\/\/zh-cn",
                "headers": {
                    "Host": "sg1.sanfencdn2.com"
                },
                "max_early_data": 0,
                "early_data_header_name": "Sec-WebSocket-Protocol"
            }
        },
        {
            "tag": "@fnet00 | DE🇩🇪 | 91.107.131.254:8443 | 144.97ms | 0️⃣1️⃣ | 32",
            "type": "vmess",
            "server": "91.107.131.254",
            "server_port": 8443,
            "uuid": "49e6b8ea-00a8-4a4d-c53b-b950050ef79c",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            }
        },
        {
            "tag": "@v2Line | FR🇫🇷 | 141.94.222.208:2082 | 150.02ms | 0️⃣1️⃣ | 33",
            "type": "vmess",
            "server": "141.94.222.208",
            "server_port": 2082,
            "uuid": "a79e03ad-84a7-41f6-bce9-e4c53180c507",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            },
            "transport": {
                "type": "ws",
                "path": "\/\/vmess",
                "headers": {
                    "Host": "141.94.222.208"
                },
                "max_early_data": 0,
                "early_data_header_name": "Sec-WebSocket-Protocol"
            }
        },
        {
            "tag": "@v2Line | GB🇬🇧 | vuk2.0bad.com:443 | 195ms | 0️⃣2️⃣ | 34",
            "type": "vmess",
            "server": "vuk2.0bad.com",
            "server_port": 443,
            "uuid": "927094d3-d678-4763-8591-e240d0bcae87",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            },
            "tls": {
                "enabled": true,
                "server_name": "vuk2.0bad.com",
                "insecure": true,
                "disable_sni": false,
                "utls": {
                    "enabled": true,
                    "fingerprint": "chrome"
                }
            },
            "transport": {
                "type": "ws",
                "path": "\/\/chat",
                "headers": {
                    "Host": "vuk2.0bad.com"
                },
                "max_early_data": 0,
                "early_data_header_name": "Sec-WebSocket-Protocol"
            }
        },
        {
            "tag": "@vmessiran | US🇺🇸 | 158.101.7.8:80 | 56.56ms | 0️⃣1️⃣ | 35",
            "type": "vmess",
            "server": "158.101.7.8",
            "server_port": 80,
            "uuid": "95b45c49-f5c0-4959-bb64-2b8fbc4a869c",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            },
            "transport": {
                "type": "ws",
                "path": "\/\/",
                "headers": {
                    "Host": "158.101.7.8"
                },
                "max_early_data": 0,
                "early_data_header_name": "Sec-WebSocket-Protocol"
            }
        },
        {
            "tag": "@vmessiran | US🇺🇸 | a7.iraniancp.fun:8880 | 113.72ms | 0️⃣2️⃣ | 36",
            "type": "vmess",
            "server": "104.16.209.12",
            "server_port": 8880,
            "uuid": "0c664f44-9f69-454f-841a-4616715df26f",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            },
            "transport": {
                "type": "ws",
                "path": "\/\/",
                "headers": {
                    "Host": "a7.iraniancp.fun"
                },
                "max_early_data": 0,
                "early_data_header_name": "Sec-WebSocket-Protocol"
            }
        },
        {
            "tag": "@Awlix_ir | US🇺🇸 | jofdji.irancel-mokhabera-mamad-raitel-mic-irancel-hamrah-aval-server.shop:2053 | 48.39ms | 0️⃣1️⃣ | 37",
            "type": "vmess",
            "server": "104.31.16.252",
            "server_port": 2053,
            "uuid": "2b1a8201-5edd-4ce0-a9d3-9b723b01ffdb",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            },
            "tls": {
                "enabled": true,
                "server_name": "jofdji.irancel-mokhabera-mamad-raitel-mic-irancel-hamrah-aval-server.shop",
                "insecure": true,
                "disable_sni": false,
                "utls": {
                    "enabled": true,
                    "fingerprint": "chrome"
                }
            },
            "transport": {
                "type": "grpc",
                "service_name": "",
                "idle_timeout": "15s",
                "ping_timeout": "15s",
                "permit_without_stream": false
            }
        },
        {
            "tag": "@Awlix_ir | RELAY🚩 | jofdji.irancel-mokhabera-mamad-raitel-mic-irancel-hamrah-aval-server.shop:2053 | 9.49ms | 0️⃣2️⃣ | 38",
            "type": "vmess",
            "server": "104.24.9.176",
            "server_port": 2053,
            "uuid": "afe90a59-7d35-4f95-8152-1b8e1b228b41",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            },
            "tls": {
                "enabled": true,
                "server_name": "jofdji.irancel-mokhabera-mamad-raitel-mic-irancel-hamrah-aval-server.shop",
                "insecure": true,
                "disable_sni": false,
                "utls": {
                    "enabled": true,
                    "fingerprint": "chrome"
                }
            },
            "transport": {
                "type": "grpc",
                "service_name": "",
                "idle_timeout": "15s",
                "ping_timeout": "15s",
                "permit_without_stream": false
            }
        },
        {
            "tag": "@Awlix_ir | US🇺🇸 | jofdji.irancel-mokhabera-mamad-raitel-mic-irancel-hamrah-aval-server.shop:2053 | 9.25ms | 0️⃣3️⃣ | 39",
            "type": "vmess",
            "server": "104.31.16.252",
            "server_port": 2053,
            "uuid": "bafa3176-341a-4106-9692-a5aad8abea42",
            "security": "auto",
            "alter_id": 0,
            "global_padding": false,
            "authenticated_length": true,
            "packet_encoding": "",
            "multiplex": {
                "enabled": false,
                "protocol": "smux",
                "max_streams": 32
            },
            "tls": {
                "enabled": true,
                "server_name": "jofdji.irancel-mokhabera-mamad-raitel-mic-irancel-hamrah-aval-server.shop",
                "insecure": true,
                "disable_sni": false,
                "utls": {
                    "enabled": true,
                    "fingerprint": "chrome"
                }
            },
            "transport": {
                "type": "grpc",
                "service_name": "",
                "idle_timeout": "15s",
                "ping_timeout": "15s",
                "permit_without_stream": false
            }
        },
        {
            "tag": "direct",
            "type": "direct"
        },
        {
            "tag": "bypass",
            "type": "direct"
        },
        {
            "tag": "block",
            "type": "block"
        },
        {
            "tag": "dns-out",
            "type": "dns"
        }
    ],
    "route": {
        "auto_detect_interface": true,
        "override_android_vpn": true,
        "final": "proxy",
        "geoip": {
            "download_url": "https:\/\/github.com\/malikshi\/sing-box-geo\/releases\/latest\/download\/geoip.db",
            "download_detour": "direct"
        },
        "geosite": {
            "download_url": "https:\/\/github.com\/malikshi\/v2ray-rules-dat\/releases\/latest\/download\/geosite.db",
            "download_detour": "direct"
        },
        "rules": [
            {
                "outbound": "dns-out",
                "port": [
                    53
                ]
            },
            {
                "inbound": [
                    "dns-in"
                ],
                "outbound": "dns-out"
            },
            {
                "domain_suffix": [
                    "ir"
                ],
                "outbound": "bypass"
            },
            {
                "geoip": [
                    "ir"
                ],
                "outbound": "bypass"
            },
            {
                "ip_cidr": [
                    "224.0.0.0\/3",
                    "ff00::\/8"
                ],
                "outbound": "block",
                "source_ip_cidr": [
                    "224.0.0.0\/3",
                    "ff00::\/8"
                ]
            }
        ]
    }
}
