# Anwesenheits-Steuerung DB (Presence Control DB)

![Home Assistant Badge](https://img.shields.io/badge/Home%20Assistant-Blueprint-blue.svg)
![Version](https://img.shields.io/badge/Version-1.4.7-green.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

---

## 🇩🇪 Beschreibung (Deutsch)

Diese umfangreiche Automatisierung steuert den Anwesenheitsstatus (Präsenz) basierend auf verschiedenen Sensoren und manuellen Auslösern. Sie ist darauf ausgelegt, Fehlsteuerungen zu minimieren und maximale Flexibilität zu bieten.

### Kernfunktionen:
* **Aktivitäts-Prüfung:** Nutzt mehrere Sensoren (Bewegung, Kontakte) zur Erkennung von Anwesenheit.
* **Schwellenwert-Logik:** Verhindert "Geister-Anwesenheit" durch einen einstellbaren Counter (z.B. erst nach 2 Impulsen innerhalb von 5 Minuten auf 'Anwesend' schalten).
* **Intelligente Abwesenheit:** Schaltet nach einer definierbaren Wartezeit auf 'Abwesend', sofern keine Aktivität mehr erkannt wird.
* **Nachtsperre über Helfer:** Über `input_datetime` Helfer lässt sich eine Sperrzeit definieren, in der die Automatik nicht auf 'Abwesend' schaltet (ideal für die Schlafenszeit).
* **Sofort-Abwesend Auslöser:** Unterstützung für Taster, Schalter oder Buttons (auch solche, die nur den Zeitstempel aktualisieren).
* **Sofort-Aktionen:** Führt Aktionen (z.B. "Alles Aus") unmittelbar beim Drücken eines Buttons aus, während der Status-Wechsel verzögert erfolgen kann.
* **Master-Schalter:** Separate Aktivierung/Deaktivierung der Automatik für Kommen und Gehen.

---

## 🇺🇸 Description (English)

This comprehensive automation manages your presence status based on various sensors and manual triggers. It is designed to minimize false triggers and provide maximum flexibility.

### Key Features:
* **Activity Check:** Uses multiple sensors (motion, contacts) to detect presence.
* **Threshold Logic:** Prevents "ghost presence" via an adjustable counter (e.g., only switch to 'Present' after 2 triggers within 5 minutes).
* **Intelligent Absence:** Switches to 'Absent' after a definable delay, provided no more activity is detected.
* **Night Lock via Helpers:** Use `input_datetime` helpers to define a period where the automation won't switch to 'Absent' (ideal for bedtime).
* **Instant Absence Triggers:** Support for toggles, momentary switches, or buttons (including those that only update their timestamp).
* **Instant Actions:** Execute actions (e.g., "All Off") immediately when a button is pressed, while the status change can be delayed.
* **Master Switches:** Separate enable/disable toggles for auto-arriving and auto-leaving logic.

---

## 🛠 Installation & Support

### PayPal Spende - Donation
Wenn dir dieser Blueprint gefällt, freue ich mich über eine kleine Unterstützung für die Kaffeekasse:

[![PayPal Spende](https://www.paypalobjects.com/de_DE/DE/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/donate/?hosted_button_id=Y5WGESDT8LWRN)

### Import
Klicke auf den Button, um den Blueprint direkt in deine Home Assistant Instanz zu importieren (ersetze `DEINE_GITHUB_URL` in der URL unten durch den direkten Link zu deiner YAML-Datei):

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2FDEINE_GITHUB_URL_HIER)

---

### 📋 Voraussetzungen - Requirements
* Ein `input_boolean` für den Anwesenheitsstatus.
* Ein `counter` Helfer für die Impuls-Logik.
* Zwei `input_datetime` Helfer (nur Uhrzeit) für die Nachtsperre.
* Zwei `input_boolean` Helfer als Master-Schalter.

---
**Autor:** D.B.  
**Lizenz:** MIT
