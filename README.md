# CryptoTTGO T DISPLAY Esp32Api
alimentation en temps réel de la valeur bitcoin et ethéréum 
Voici un **README complet**, clair et propre pour ton dépôt GitHub, adapté à un projet **TTGO T‑Display** affichant en quasi temps réel le **Bitcoin** et l’**Ethereum** via **deux clés API**.  
Il est structuré comme un vrai README pro, prêt à copier‑coller dans ton repo.

J’intègre des **Guided Links** sur les termes que tu pourrais vouloir développer ensuite.

---

# 📟 TTGO T‑Display – Crypto Ticker (BTC / ETH)

Affichage en temps quasi réel du **Bitcoin** et de l’**Ethereum** sur un **TTGO T‑Display ESP32**, grâce à deux clés API (une pour chaque crypto).  
Le projet interroge une API externe toutes les X secondes et met à jour l’écran TFT intégré.

---

## 🚀 Fonctionnalités

- Affichage en direct du **prix du Bitcoin**  
- Affichage en direct du **prix de l’Ethereum**  
- Rafraîchissement automatique (intervalle configurable)  
- Connexion WiFi intégrée  
- Compatible avec les API type **CoinAPI**, **CoinGecko**, **Binance**, etc.  
- Code optimisé pour l’écran **ST7789** du TTGO T‑Display

---

## 🧰 Matériel nécessaire

- 1 × **TTGO T‑Display ESP32**  
- 1 × câble USB‑C  
- Connexion WiFi  
- 2 clés API (BTC + ETH)

---

## 🔧 Installation

### 1. Cloner le dépôt

```bash
git clone https://github.com/tonpseudo/ton-repo.git
cd ton-repo
```

### 2. Installer les dépendances Arduino

Dans l’IDE Arduino, installe :

- **TFT_eSPI**  
- **ArduinoJson**  
- **WiFi.h** (déjà inclus dans ESP32)  
- **HTTPClient.h** (déjà inclus)

### 3. Configurer TFT_eSPI

Dans `TFT_eSPI/User_Setup_Select.h`, activer :

```cpp
#include <User_Setups/Setup25_TTGO_T_Display.h>
```

### 4. Ajouter vos clés API

Dans `config.h` :

```cpp
#define WIFI_SSID "TonWifi"
#define WIFI_PASS "TonMotDePasse"

#define API_KEY_BTC "ta_cle_api_bitcoin"
#define API_KEY_ETH "ta_cle_api_ethereum"
```

---

## 📡 Exemple d’appel API

```cpp
HTTPClient http;
http.begin("https://api.exemple.com/v1/btc?apikey=" + String(API_KEY_BTC));
int code = http.GET();
```

---

## 🖥️ Affichage sur le TTGO T‑Display

Le code affiche :

- BTC : prix en USD  
- ETH : prix en USD  
- Dernière mise à jour  
- Couleur verte si le prix monte, rouge si baisse (optionnel)

---

## ⚙️ Configuration

Dans `main.cpp` :

```cpp
#define REFRESH_INTERVAL 5000  // en millisecondes
```

---

## 📁 Structure du projet

```
/src
  main.cpp
  config.h
/lib
  TFT_eSPI
  ArduinoJson
README.md
```

---

## 🧪 Améliorations possibles

- Ajouter d’autres cryptos  
- Ajouter un graphique mini‑sparkline  
- Mode sombre / clair  
- Animation lors des mises à jour  
- Support MQTT

---

## 📜 Licence

MIT — libre d’utilisation et de modification.

---

## 🔗 Liens utiles

- **Documentation TTGO T‑Display**  
- **API Bitcoin**  
- **API Ethereum**  
- **Configurer TFT_eSPI**  

---

