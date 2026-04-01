# Anwesenheits-Steuerung DB / Attendance Control DB

<div align="center">
    <p><strong>Version 1.2</strong> | <strong>Autor: D.B.</strong></p>
    
    <a href="https://www.paypal.com/donate/?hosted_button_id=Y5WGESDT8LWRN" target="_blank">
        <img src="https://img.shields.io/badge/Donate-PayPal-blue.svg" alt="PayPal">
    </a>
    &nbsp;&nbsp;
    <a href="https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Fdavid883%2FHome-Assistant-by-DB%2Frefs%2Fheads%2Fmain%2Fblueprints%2Fautomation%2FDB%2FAttendance%2520control%2FAttendance%2520control%2520DB.yaml" target="_blank">
        <img src="https://my.home-assistant.io/badges/blueprint_import.svg" alt="Import Blueprint">
    </a>
</div>

---

## 🇩🇪 Deutsch: Beschreibung
Diese Home Assistant Automatisierung (Blueprint) bietet eine intelligente und hochflexible Lösung zur Verwaltung deines Anwesenheitsstatus. Sie kombiniert klassische Bewegungsmelder mit beliebigen anderen Sensoren und Schaltern, um präzise zu erkennen, ob jemand zu Hause ist oder nicht.

### Hauptfunktionen:
* **Multi-Sensor-Aktivität:** Nutze nicht nur Bewegungsmelder, sondern auch Lichtschalter, Türkontakte oder Mediaplayer. Du entscheidest, welche Zustände (z.B. `on`, `motion`, `playing`) als Aktivität gelten.
* **Fehlalarm-Schutz (Counter):** Erst wenn innerhalb eines definierten Zeitfensters eine bestimmte Anzahl an Impulsen erreicht wird, schaltet das System auf "Anwesend".
* **Nacht-Sperre (Schlafmodus):** Definiere ein Zeitfenster (z.B. 22:00 - 08:00 Uhr), in dem das System **nicht** auf abwesend schalten darf.
* **Sofort-Abwesenheits-Schalter:** Nutze Taster oder Türschlösser, um sofort (oder mit einer einstellbaren Verzögerung) beim Verlassen auf "Abwesend" zu schalten.
* **Getrennte Master-Schalter:** Aktiviere oder deaktiviere die automatische Erkennung für "Kommen" und "Gehen" separat.

---

## 🇺🇸 English: Description
This Home Assistant automation (blueprint) provides an intelligent and highly flexible solution for managing your presence status. It combines classic motion sensors with any other sensors or switches to accurately detect whether someone is at home or not.

### Main Features:
* **Multi-Sensor Activity:** Use motion sensors, light switches, door contacts, or media players. You decide which states (e.g., `on`, `motion`, `playing`) count as activity.
* **False Alarm Protection (Counter):** The system only switches to "Present" once a defined number of triggers are reached within a specific time window.
* **Night Lock (Sleep Mode):** Define a time window (e.g., 10:00 PM - 08:00 AM) during which the system is **prohibited** from switching to "Absent."
* **Instant Absence Switch:** Use buttons or smart locks to trigger "Absent" status immediately (or with a configurable delay) when leaving.
* **Separate Master Switches:** Enable or disable automatic detection for "Arriving" and "Leaving" separately.

---

<div align="center">
    <p>If you like this blueprint, feel free to support my work!</p>
    <a href="https://www.paypal.com/donate/?hosted_button_id=Y5WGESDT8LWRN" target="_blank">
        <img src="https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif" alt="PayPal Donate">
    </a>
</div>
