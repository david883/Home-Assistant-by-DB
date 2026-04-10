# Zigbee Statusüberwachung (Batteriegeräte) 🌐

Dieser Blueprint ermöglicht eine intelligente Überwachung von Zigbee2Mqtt Entitäten auf ihre Erreichbarkeit. Im Gegensatz zu einfachen Automatisierungen nutzt dieses Script ein erweitertes Gedächtnis (Input Select), um den Status mehrerer Geräte gleichzeitig zu verwalten und dynamische Listen der aktuell nicht erreichbaren Geräte zu erstellen.

---

### ☕ Dir gefällt meine Arbeit? / Do you like my work?

[![PayPal Spende](https://www.paypalobjects.com/de_DE/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/donate/?hosted_button_id=Y5WGESDT8LWRN)

---

## 📖 Funktionen / Features

* **Intelligentes Gedächtnis:** Nutzt einen `input_select` Helfer, um den Überblick über alle Offline-Geräte zu behalten.
* **Dynamische Listen:** In den Benachrichtigungen wird automatisch aufgelistet, welche anderen Geräte ebenfalls gerade offline sind.
* **Verzögerungsfilter:** Einstellbare Wartezeiten für Online- und Offline-Events, um Fehlalarme bei kurzen Verbindungsabbrüchen zu vermeiden.
* **Dashboard-Integration:** Ein Zähler-Helfer ermöglicht die einfache Anzeige der überwachten Geräte auf deinem Dashboard.
* **Neustart-Schutz:** Verhindert Fehlalarme während Home Assistant oder Zigbee2Mqtt neu gestartet werden.

## 🛠 Voraussetzungen / Prerequisites

1.  **Zigbee2Mqtt:** Die Option `last_seen` muss in den Zigbee2Mqtt-Einstellungen aktiviert sein.
2.  **Helfer (Helpers):**
    * **Input Select:** Ein Dropdown-Helfer für das Gedächtnis (muss die Option `Platzhalter` enthalten).
    * **Input Number:** Ein Nummern-Helfer für den Dashboard-Zähler.
    * **Input Text (Optional):** Falls du Nachrichten über einen Text-Helfer verarbeiten möchtest.

## 🚀 Installation

[![Import Blueprint to HA](https://img.shields.io/badge/Import%20Blueprint-to%20HA-blue?style=for-the-badge&logo=homeassistant)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2Fdavid883%2FHome-Assistant-by-DB%2Fblob%2Fmain%2Fblueprints%2Fautomation%2FDB%2FZigbee%2520Status%2520Monitoring%2FZigbee%2520Status%2520Monitoring%2520DB.yaml)

1.  Klicke auf den Button oben, um den Blueprint zu importieren.
2.  Erstelle die benötigten Helfer in Home Assistant.
3.  Erstelle eine neue Automatisierung basierend auf diesem Blueprint.

## 📝 Variablen für Aktionen / Action Variables

Folgende Variablen können in den Aktionen (z.B. für Benachrichtigungen) verwendet werden:

| Variable | Beschreibung (DE) | Description (EN) |
| :--- | :--- | :--- |
| `{{ device }}` | Name des betroffenen Geräts. | Affected device. |
| `{{ list }}` | Andere Offline-Geräte (max. 3 Namen). | Other offline devices (max 3 names). |
| `{{ count }}` | Gesamtzahl der überwachten Geräte. | Total number of monitored devices. |
| `{{ threshold }}` | Offline Schwellenwert in Minuten. | Offline threshold in minutes. |
| `{{ minutes_since }}` | Minuten seit der letzten Meldung. | Minutes since last seen report. |

## 📊 Dashboard Integration (Markdown)

Du kannst diesen Code in einer Markdown-Karte nutzen, um den Status anzuzeigen. Vorher musst du hier statt DEIN HELFER natürlich deine Datenpunkte einfügen.

```yaml
type: markdown
content: >
  {% set total = states('input_number.DEIN_HELFER') | int(0) %}
  ### 🌐 Zigbee Netzwerk-Status
  **Überwachte Geräte gesamt:** {{ total }}
  ---
  {% set offline_options = state_attr('input_select.DEIN_HELFER', 'options') %}
  {% set real_offline = offline_options | reject('eq', 'Platzhalter') | list if offline_options is not none else [] %}
  {% if real_offline | count > 0 %}
    ⚠️ **Aktuell offline ({{ real_offline | count }}):**
    {% for ent in real_offline %}
      - {{ state_attr(ent, 'friendly_name') | replace(' Last seen', '') }}
    {% endfor %}
  {% else %}
    ✅ **Alle Geräte sind online.**
  {% endif %}
