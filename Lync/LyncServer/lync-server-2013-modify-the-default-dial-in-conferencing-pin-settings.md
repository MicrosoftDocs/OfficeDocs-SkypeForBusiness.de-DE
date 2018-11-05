---
title: 'Lync Server 2013: Ändern der Standard-PIN-Einstellungen für Einwahlkonferenzen'
TOCTitle: Ändern der Standard-PIN-Einstellungen für Einwahlkonferenzen
ms:assetid: 2d110e94-ad29-4755-b17f-d8c2da9b78a4
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425780(v=OCS.15)
ms:contentKeyID: 49293532
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ändern der Standard-PIN-Einstellungen für Einwahlkonferenzen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-18_

In der globalen PIN-Richtlinie werden die Regeln für Einwahlkonferenz-PINs auf Gesamtstrukturebene definiert. Führen Sie die folgenden Schritte aus, um die globale Richtlinie für Einwahlkonferenz-PINs zu ändern. Ausführliche Informationen zur Erstellung oder Änderung einer Richtlinie für Einwahlkonferenz-PINs auf Standort- oder Benutzerebene finden Sie unter [Erstellen oder Ändern der PIN-Einstellungen für Einwahlkonferenzen für einen Standort oder eine Benutzergruppe in Lync Server 2013](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).

## So ändern Sie die globale PIN-Richtlinie

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer des Netzwerks an, in dem Sie Lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **PIN-Richtlinie** .

4.  Klicken Sie auf der Seite **PIN-Richtlinie** auf **Global** , klicken Sie auf **Bearbeiten** , und klicken Sie dann auf **Details anzeigen** .

5.  Geben Sie unter **PIN-Richtlinie bearbeiten** im Feld **PIN-Mindestlänge** die gewünschte Mindestlänge für die PIN ein, oder wählen Sie sie aus. In der Standardeinstellung beträgt die Mindestlänge fünf Ziffern.

6.  Aktivieren Sie das Kontrollkästchen **Maximale Anzahl von Anmeldeversuchen angeben** , um anzugeben, nach wie vielen erfolglosen Anmeldeversuchen ein Benutzer gesperrt wird. Wenn Sie diese Option nicht aktivieren, wird die maximale Anzahl von Anmeldeversuchen basierend auf der PIN-Länge automatisch festgelegt. In der Standardeinstellung wird die maximale Anzahl von Anmeldeversuchen automatisch festgelegt.

7.  Wenn Sie das Kontrollkästchen **Maximale Anzahl von Anmeldeversuchen angeben** aktiviert haben, geben Sie in **Maximale Anzahl von Anmeldeversuchen** die maximale Anzahl von Anmeldeversuchen ein, die Sie zulassen möchten. Sie können auch einen Wert auswählen.

8.  Aktivieren Sie das Kontrollkästchen **PIN-Ablauf aktivieren** , um eine PIN-Ablaufdauer festzulegen. Wenn Sie diese Option nicht aktivieren, laufen PINs nie ab. In der Standardeinstellung ist für PINs kein Ablauf festgelegt.

9.  Wenn Sie das Kontrollkästchen **PIN-Ablauf aktivieren** aktiviert haben, geben Sie unter **PIN-Ablauf nach (Tagen)** die Anzahl von Tagen ein, nach der PINs ablaufen.

10. Geben Sie unter **PIN-Verlaufszähler** die Anzahl von PINs ein, die ein Benutzer erstellen muss, bevor eine PIN erneut verwendet werden kann. In der Standardeinstellung können Benutzer ihre PINs erneut verwenden.

11. Aktivieren Sie das Kontrollkästchen **Allgemeine Muster zulassen** , um allgemeine Muster in PINs zuzulassen, beispielsweise aufeinanderfolgende und wiederholte Zahlen. Wenn Sie diese Option nicht aktivieren, sind nur komplexe Ziffernmuster zulässig. In der Standardeinstellung dürfen nur komplexe Ziffernmuster verwendet werden.
    

    > [!IMPORTANT]
    > Es wird empfohlen, die Verwendung gängiger Muster nicht zuzulassen.



12. Klicken Sie auf **Commit** .

