# Zigbee Statusüberwachung / Zigbee Status Monitoring 🌐

🇩🇪 Dieser Blueprint ermöglicht eine intelligente Überwachung von Zigbee2Mqtt Entitäten auf ihre Erreichbarkeit. Im Gegensatz zu einfachen Automatisierungen nutzt dieses Script ein erweitertes Gedächtnis (Input Select), um den Status mehrerer Geräte gleichzeitig zu verwalten und dynamische Listen der aktuell nicht erreichbaren Geräte zu erstellen.

🇬🇧 This blueprint allows intelligent monitoring of Zigbee2Mqtt entities for availability. Unlike simple automations, this script uses an extended memory (Input Select) to manage the status of multiple devices simultaneously and create dynamic lists of currently unreachable devices.

---

### ☕ Dir gefällt meine Arbeit? / Do you like my work?

[![PayPal Spende](https://www.paypalobjects.com/de_DE/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/donate/?hosted_button_id=Y5WGESDT8LWRN)

---

## 📖 Funktionen / Features

* 🇩🇪 **Intelligentes Gedächtnis:** Nutzt einen `input_select` Helfer, um den Überblick über alle Offline-Geräte zu behalten.
* 🇬🇧 **Intelligent Memory:** Uses an `input_select` helper to track all offline devices.
* 🇩🇪 **Dynamische Listen:** In den Benachrichtigungen wird automatisch aufgelistet, welche anderen Geräte ebenfalls gerade offline sind.
* 🇬🇧 **Dynamic Lists:** Automatically lists other offline devices in notifications.
* 🇩🇪 **Verzögerungsfilter:** Einstellbare Wartezeiten für Online- und Offline-Events.
* 🇬🇧 **Delay Filter:** Adjustable wait times for online and offline events.
* 🇩🇪 **Dashboard-Integration:** Ein Zähler-Helfer ermöglicht die einfache Anzeige der überwachten Geräte.
* 🇬🇧 **Dashboard Integration:** A counter helper allows for easy display of monitored devices.

## 🛠 Voraussetzungen / Prerequisites

1.  **Zigbee2Mqtt:** 🇩🇪 Die Option `last_seen` muss aktiviert sein. / 🇬🇧 The `last_seen` option must be enabled.
2.  **Helfer / Helpers:**
    * **Input Select:** 🇩🇪 Gedächtnis-Helfer (muss die Option `Platzhalter` enthalten). / 🇬🇧 Memory helper (must contain the option `Platzhalter`).
    * **Input Number:** 🇩🇪 Dashboard-Zähler. / 🇬🇧 Dashboard counter.

## 🚀 Installation

[![Import Blueprint to HA](https://img.shields.io/badge/Import%20Blueprint-to%20HA-blue?style=for-the-badge&logo=homeassistant)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2Fdavid883%2FHome-Assistant-by-DB%2Fblob%2Fmain%2Fblueprints%2Fautomation%2FDB%2FZigbee%2520Status%2520Monitoring%2FZigbee%2520Status%2520Monitoring%2520DB.yaml)

## 📝 Variablen für Aktionen / Action Variables

| Variable | Beschreibung (DE) | Description (EN) |
| :--- | :--- | :--- |
| `{{ device }}` | Name des betroffenen Geräts. | Affected device. |
| `{{ list }}` | Andere Offline-Geräte (max. 3 Namen). | Other offline devices (max 3 names). |
| `{{ count }}` | Gesamtzahl der überwachten Geräte. | Total number of monitored devices. |
| `{{ threshold }}` | Offline Schwellenwert in Minuten. | Offline threshold in minutes. |
| `{{ minutes_since }}` | Minuten seit der letzten Meldung. | Minutes since last seen report. |

## 📊 Dashboard Integration (Markdown)

🇩🇪 Du kannst diesen Code in einer Markdown-Karte nutzen, um den Status anzuzeigen. Vorher musst du hier statt DEIN HELFER natürlich deine Datenpunkte einfügen.

🇬🇧 You can use this code in a Markdown card to display the status. You must replace DEIN HELFER with your actual data points first.

```yaml
type: markdown
content: >
  {% set total = states('input_number.DEIN_HELFER') | int(0) %}
  ### 🌐 Zigbee Netzwerk-Status / Network Status
  **Überwachte Geräte gesamt / Total monitored:** {{ total }}
  ---
  {% set offline_options = state_attr('input_select.DEIN_HELFER', 'options') %}
  {% set real_offline = offline_options | reject('eq', 'Platzhalter') | list if offline_options is not none else [] %}
  {% if real_offline | count > 0 %}
    ⚠️ **Aktuell offline / Currently offline ({{ real_offline | count }}):**
    {% for ent in real_offline %}
      - {{ state_attr(ent, 'friendly_name') | replace(' Last seen', '') }}
    {% endfor %}
  {% else %}
    ✅ **Alle Geräte sind online. / All devices are online.**
  {% endif %}
