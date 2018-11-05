---
title: Ändern einer vorhandenen PIN-Richtlinie
TOCTitle: Ändern einer vorhandenen PIN-Richtlinie
ms:assetid: 517caaee-3349-4fa6-8d86-e4da3258a445
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg520993(v=OCS.15)
ms:contentKeyID: 49293996
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ändern einer vorhandenen PIN-Richtlinie

 

_**Letztes Änderungsdatum des Themas:** 2012-06-19_

Auf der Registerkarte **PIN-Richtlinie** können Sie Benutzern, die sich über IP-Telefone mit Lync 2013 verbinden, eine PIN-Authentifizierung (persönliche Identifikationsnummer) bereitstellen. Stellen Sie zur Verwendung der PIN-Authentifizierung sicher, dass in den Webdiensteinstellungen die Option **PIN-Authentifizierung aktivieren** ausgewählt ist. Ausführliche Informationen hierzu finden Sie unter [Ändern von vorhandenen Webdienst-Konfigurationseinstellungen](lync-server-2013-modify-existing-web-service-configuration-settings.md).

Führen Sie die folgenden Schritte aus, um eine PIN-Richtlinie auf Benutzer- oder Standortebene zu ändern.

## So ändern Sie eine vorhandene PIN-Richtlinie

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer des Netzwerks an, in dem Sie Lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **PIN-Richtlinie**.

4.  Klicken Sie auf der Seite **PIN-Richtlinie** auf eine Richtlinie, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  Geben Sie unter **PIN-Richtlinie bearbeiten** im Feld **PIN-Mindestlänge** die gewünschte Mindestlänge für die PIN ein, oder wählen Sie sie aus. In der Standardeinstellung beträgt die Mindestlänge fünf Ziffern.

6.  Aktivieren Sie das Kontrollkästchen **Maximale Anmeldeversuche angeben**, um anzugeben, nach wie vielen erfolglosen Anmeldeversuchen ein Benutzer gesperrt wird. Wenn Sie diese Option nicht aktivieren, wird die maximale Anzahl von Anmeldeversuchen basierend auf der PIN-Länge automatisch festgelegt. In der Standardeinstellung wird die maximale Anzahl von Anmeldeversuchen automatisch festgelegt.

7.  Wenn Sie das Kontrollkästchen **Maximale Anmeldeversuche angeben** aktiviert haben, geben Sie in **Maximale Anmeldeversuche** die maximale Anzahl von Anmeldeversuchen ein, die Sie zulassen möchten. Sie können auch einen Wert auswählen.

8.  Aktivieren Sie das Kontrollkästchen **PIN-Ablauf aktivieren**, um eine PIN-Ablaufdauer festzulegen. Wenn Sie diese Option nicht aktivieren, laufen PINs nie ab. In der Standardeinstellung ist für PINs kein Ablauf festgelegt.

9.  Wenn Sie das Kontrollkästchen **PIN-Ablauf aktivieren** aktiviert haben, geben Sie unter **PIN läuft ab nach (Tagen)** die Anzahl von Tagen ein, nach der PINs ablaufen.

10. Geben Sie unter **PIN-Verlaufszähler** die Anzahl von PINs ein, die ein Benutzer erstellen muss, bevor eine PIN erneut verwendet werden kann. In der Standardeinstellung können Benutzer ihre PINs erneut verwenden.

11. Aktivieren Sie das Kontrollkästchen **Gängige Muster zulassen**, um gängige Muster in PINs zuzulassen, beispielsweise aufeinanderfolgende und wiederholte Zahlen. Wenn Sie diese Option nicht aktivieren, sind nur komplexe Ziffernmuster zulässig. In der Standardeinstellung dürfen nur komplexe Ziffernmuster verwendet werden.
    

    > [!IMPORTANT]
    > Es wird empfohlen, die Verwendung gängiger Muster nicht zuzulassen.



12. Klicken Sie auf **Commit**.

