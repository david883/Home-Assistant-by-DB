# Anwesenheits-Steuerung DB (Presence Control DB)

![Home Assistant Badge](https://img.shields.io/badge/Home%20Assistant-Blueprint-blue.svg)
![Version](https://img.shields.io/badge/Version-1.4.7-green.svg)
![License](https://img.shields.io/badge/License-GPL%203.0-red.svg)

---

## 🇩🇪 Beschreibung (Deutsch)

Diese umfangreiche Automatisierung steuert den Anwesenheitsstatus (Präsenz) basierend auf verschiedenen Sensoren und manuellen Auslösern. Sie ist darauf ausgelegt, Fehlsteuerungen zu minimieren und maximale Flexibilität zu bieten.

### Kernfunktionen:
* **Aktivitäts-Prüfung:** Nutzt mehrere Sensoren (Bewegung, Kontakte) zur Erkennung von Anwesenheit.
* **Schwellenwert-Logik:** Verhindert "Geister-Anwesenheit" durch einen einstellbaren Counter (z.B. erst nach 2 Impulsen innerhalb von 5 Minuten auf 'Anwesend' schalten).
* **Intelligente Abwesenheit:** Schaltet nach einer definierbaren Wartezeit auf 'Abwesend', sofern keine Aktivität mehr erkannt wird.
* **Nachtsperre:** Eine Sperrzeit definieren, in der die Automatik nicht auf 'Abwesend' schaltet (ideal für die Schlafenszeit).
* **Master-Schalter:** Separate Aktivierung/Deaktivierung der Automatik für Kommen und Gehen.

---

## 🇺🇸 Description (English)

This comprehensive automation manages your presence status based on various sensors and manual triggers. It is designed to minimize false triggers and provide maximum flexibility.

### Key Features:
* **Activity Check:** Uses multiple sensors (motion, contacts) to detect presence.
* **Threshold Logic:** Prevents "ghost presence" via an adjustable counter (e.g., only switch to 'Present' after 2 triggers within 5 minutes).
* **Intelligent Absence:** Switches to 'Absent' after a definable delay, provided no more activity is detected.
* **Night Lock:** Define a period where the automation won't switch to 'Absent' (ideal for bedtime).
* **Master Switches:** Separate enable/disable toggles for auto-arriving and auto-leaving logic.

---

## 🛠 Installation & Support

### PayPal Spende - Donation
Wenn dir dieser Blueprint gefällt, freue ich mich über eine kleine Unterstützung für die Kaffeekasse:

[![PayPal Spende](https://www.paypalobjects.com/de_DE/DE/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/donate/?hosted_button_id=Y5WGESDT8LWRN)

### Import
Klicke auf den Button, um den Blueprint direkt in deine Home Assistant Instanz zu importieren:

[![Blueprint Import](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2Fdavid883%2FHome-Assistant-by-DB%2Fblob%2Fmain%2Fblueprints%2Fautomation%2FDB%2FAttendance%2520control%2FAttendance%2520control%2520DB.yaml)

---

### 📋 Voraussetzungen - Requirements
* Ein `input_boolean` für den Anwesenheitsstatus.
* Ein `counter` Helfer für die Impuls-Logik.
* Zwei `input_datetime` Helfer (nur Uhrzeit) für die Nachtsperre.
* Zwei `input_boolean` Helfer als Master-Schalter.

---
**Autor:** D.B.  
**Lizenz:** GNU GPL v3.0
