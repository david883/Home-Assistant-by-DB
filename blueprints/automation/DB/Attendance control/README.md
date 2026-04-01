<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
</head>
<body>

    <div align="center">
        <h1>Anwesenheits-Steuerung DB / Attendance Control DB</h1>
        <p><strong>Version 1.2</strong> | <strong>Autor: D.B.</strong></p>
        
        <a href="https://www.paypal.com/donate/?hosted_button_id=Y5WGESDT8LWRN" target="_blank">
            <img src="https://img.shields.io/badge/Donate-PayPal-blue.svg" alt="PayPal">
        </a>
        <br><br>
        <a href="https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Fdavid883%2FHome-Assistant-by-DB%2Frefs%2Fheads%2Fmain%2Fblueprints%2Fautomation%2FDB%2FAttendance%2520control%2FAttendance%2520control%2520DB.yaml" target="_blank">
            <img src="https://my.home-assistant.io/badges/blueprint_import.svg" alt="Import Blueprint">
        </a>
    </div>

    <hr>

    <section>
        <h2>🇩🇪 Deutsch: Beschreibung</h2>
        <p>
            Diese Home Assistant Automatisierung (Blueprint) bietet eine intelligente und hochflexible Lösung zur Verwaltung deines Anwesenheitsstatus. 
            Sie kombiniert klassische Bewegungsmelder mit beliebigen anderen Sensoren und Schaltern, um präzise zu erkennen, ob jemand zu Hause ist oder nicht.
        </p>
        <h3>Hauptfunktionen:</h3>
        <ul>
            <li><strong>Multi-Sensor-Aktivität:</strong> Nutze nicht nur Bewegungsmelder, sondern auch Lichtschalter, Türkontakte oder Mediaplayer. Du entscheidest, welche Zustände (z.B. <code>on</code>, <code>motion</code>, <code>playing</code>) als Aktivität gelten.</li>
            <li><strong>Fehlalarm-Schutz (Counter):</strong> Erst wenn innerhalb eines definierten Zeitfensters eine bestimmte Anzahl an Impulsen erreicht wird, schaltet das System auf "Anwesend".</li>
            <li><strong>Nacht-Sperre (Schlafmodus):</strong> Definiere ein Zeitfenster (z.B. 22:00 - 08:00 Uhr), in dem das System <strong>nicht</strong> auf abwesend schalten darf.</li>
            <li><strong>Sofort-Abwesenheits-Schalter:</strong> Nutze Taster oder Türschlösser, um sofort (oder mit einer einstellbaren Verzögerung) beim Verlassen auf "Abwesend" zu schalten.</li>
            <li><strong>Getrennte Master-Schalter:</strong> Aktiviere oder deaktiviere die automatische Erkennung für "Kommen" und "Gehen" separat.</li>
        </ul>
    </section>

    <hr>

    <section>
        <h2>🇺🇸 English: Description</h2>
        <p>
            This Home Assistant automation (blueprint) provides an intelligent and highly flexible solution for managing your presence status. 
            It combines classic motion sensors with any other sensors or switches to accurately detect whether someone is at home or not.
        </p>
        <h3>Main Features:</h3>
        <ul>
            <li><strong>Multi-Sensor Activity:</strong> Use motion sensors, light switches, door contacts, or media players. You decide which states (e.g., <code>on</code>, <code>motion</code>, <code>playing</code>) count as activity.</li>
            <li><strong>False Alarm Protection (Counter):</strong> The system only switches to "Present" once a defined number of triggers are reached within a specific time window.</li>
            <li><strong>Night Lock (Sleep Mode):</strong> Define a time window (e.g., 10:00 PM - 08:00 AM) during which the system is <strong>prohibited</strong> from switching to "Absent."</li>
            <li><strong>Instant Absence Switch:</strong> Use buttons or smart locks to trigger "Absent" status immediately (or with a configurable delay) when leaving.</li>
            <li><strong>Separate Master Switches:</strong> Enable or disable automatic detection for "Arriving" and "Leaving" separately.</li>
        </ul>
    </section>

    <hr>

    <div align="center">
        <p>If you like this blueprint, feel free to support my work!</p>
        <a href="https://www.paypal.com/donate/?hosted_button_id=Y5WGESDT8LWRN" target="_blank">
            <img src="https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif" alt="PayPal Donate">
        </a>
    </div>

</body>
</html>
