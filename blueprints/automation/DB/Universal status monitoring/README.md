# Universelle Statusüberwachung DB / Universal Status Monitoring DB

[![Import Blueprint to HA](https://img.shields.io/badge/Import%20Blueprint-to%20HA-blue?style=for-the-badge&logo=homeassistant)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Fdavid883%2FHome-Assistant-by-DB%2Frefs%2Fheads%2Fmain%2Fblueprints%2Fautomation%2FDB%2FUniversal%2520status%2520monitoring%2FUniversal%2520status%2520monitoring.yaml)

---

### 🇩🇪 Beschreibung
Dieser Blueprint ermöglicht eine intelligente Überwachung von Home Assistant Entitäten auf ihre Erreichbarkeit. Im Gegensatz zu einfachen Automatisierungen nutzt dieses Script ein **erweitertes Gedächtnis** (Input Select), um den Status mehrerer Geräte gleichzeitig zu verwalten und dynamische Listen der aktuell nicht erreichbaren Geräte zu erstellen.

**Kernfunktionen:**
* **Intelligentes Gedächtnis:** Nutzt einen `input_select` Helfer, um den Überblick über alle Offline-Geräte zu behalten.
* **Dynamische Listen:** In den Benachrichtigungen wird automatisch aufgelistet, welche *anderen* Geräte ebenfalls gerade offline sind.
* **Flexible Status-Definition:** Freie Auswahl, welche Zustände (z. B. `unavailable`, `unknown`, `not_home`, `off`) als "Offline" gewertet werden sollen.
* **Verzögerungsfilter:** Einstellbare Wartezeiten für Online- und Offline-Events, um Fehlalarme bei kurzen Verbindungsabbrüchen zu vermeiden.
* **Effizienz:** Aktionen werden nur bei tatsächlichen Statusänderungen im Gedächtnis ausgelöst.

---

### 🇺🇸 Description
This blueprint provides intelligent monitoring of Home Assistant entities for their availability. Unlike simple automations, this script uses an **extended memory** (Input Select) to manage the status of multiple devices simultaneously and generate dynamic lists of currently unreachable devices.

**Key Features:**
* **Smart Memory:** Uses an `input_select` helper to keep track of all offline devices.
* **Dynamic Lists:** Notifications automatically list which *other* devices are also currently offline.
* **Custom States:** Flexible selection of which states (e.g., `unavailable`, `unknown`, `not_home`, `off`) are considered "Offline".
* **Duration Filters:** Adjustable wait times for online and offline events to prevent false alarms during brief connection hiccups.
* **Efficiency:** Actions are only triggered when the status in the memory actually changes.

---

### 🛠 Einrichtung / Setup

1.  **Helfer erstellen / Create Helper:** Erstelle einen `input_select` (Auswahlliste) Helfer.
2.  **Platzhalter:** Füge der Liste als erste Option das Wort `Platzhalter` hinzu (dies dient als Basis für das Script).
3.  **Blueprint importieren:** Nutze den blauen Button oben, um den Blueprint in dein Home Assistant zu laden.
4.  **Konfigurieren:** Wähle die zu überwachenden Entitäten aus und definiere deine gewünschten Aktionen (z.B. Benachrichtigung per App).

---

### ☕ Unterstützung / Support

Dir gefällt meine Arbeit? Lade mich doch auf einen Kaffee oder ein kühles Getränk ein. Ich freue mich über jede kleine Unterstützung!

Do you like my work? Feel free to buy me a coffee or a cool drink. I appreciate any support!

[![PayPal Spende](https://www.paypalobjects.com/de_DE/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/donate/?hosted_button_id=Y5WGESDT8LWRN)

---

**Version:** 04.04.2026-16  
**Autor:** D.B.  
**Source:** [GitHub Repository](https://github.com/david883/Home-Assistant-by-DB)
