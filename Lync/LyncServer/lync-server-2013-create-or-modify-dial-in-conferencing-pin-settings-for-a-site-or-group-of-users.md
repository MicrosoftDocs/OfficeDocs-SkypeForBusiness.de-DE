---
title: 'Lync Server 2013: Erstellen oder Ändern der PIN-Einstellungen für Einwahlkonferenzen für einen Standort oder eine Benutzergruppe'
TOCTitle: Erstellen oder Ändern der PIN-Einstellungen für Einwahlkonferenzen für einen Standort oder eine Benutzergruppe
ms:assetid: c29bab5c-2b93-48e0-ae0b-29564daaff9a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412959(v=OCS.15)
ms:contentKeyID: 49295310
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Ändern der PIN-Einstellungen für Einwahlkonferenzen für einen Standort oder eine Benutzergruppe in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-18_

Führen Sie die folgenden Schritte aus, um die auf Benutzer- oder Standortebene definierte PIN-Richtlinie für Einwahlkonferenzen zu erstellen oder zu ändern. Ausführliche Informationen zum Ändern der globalen PIN-Richtlinie finden Sie unter [Ändern der Standard-PIN-Einstellungen für Einwahlkonferenzen in Lync Server 2013](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md).

## So erstellen Sie eine PIN-Richtlinie auf Benutzer- oder Standortebene

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer des Netzwerks an, in dem Sie Lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **PIN-Richtlinie** .

4.  Klicken Sie auf der Seite **PIN-Richtlinie** auf **Neu** , und führen Sie eine der folgenden Aktionen aus:
    
      - Klicken Sie auf **Hinzufügen** , um eine Richtlinie auf Benutzerebene zu erstellen. Geben Sie im Abschnitt **Neue PIN-Richtlinie** in **Name** einen beschreibenden Namen für die Richtlinie ein.
    
      - Klicken Sie auf **Standortrichtlinie** , um eine Richtlinie auf Standortebene zu erstellen. Geben Sie im Suchfeld **Standort auswählen** einen Teil oder den gesamten Namen des Standorts ein, für den Sie eine Richtlinie erstellen möchten. Klicken Sie in der Liste der Standorte auf den gewünschten Standort, und klicken Sie auf **OK** .

5.  Geben Sie im Feld **Beschreibung** eine Beschreibung für die PIN-Richtlinie ein.

6.  Geben Sie im Feld **PIN-Mindestlänge** die gewünschte Mindestlänge für die PIN ein, oder wählen Sie sie aus. In der Standardeinstellung beträgt die Mindestlänge fünf Ziffern.

7.  Aktivieren Sie das Kontrollkästchen **Maximale Anzahl von Anmeldeversuchen angeben** , um anzugeben, nach wie vielen erfolglosen Anmeldeversuchen ein Benutzer gesperrt wird. Wenn Sie diese Option nicht aktivieren, wird die maximale Anzahl von Anmeldeversuchen basierend auf der PIN-Länge automatisch festgelegt. In der Standardeinstellung wird die maximale Anzahl von Anmeldeversuchen automatisch festgelegt.

8.  Wenn Sie das Kontrollkästchen **Maximale Anzahl von Anmeldeversuchen angeben** aktiviert haben, geben Sie in **Maximale Anzahl von Anmeldeversuchen** die maximale Anzahl von Anmeldeversuchen ein, die Sie zulassen möchten. Sie können auch einen Wert auswählen.

9.  Aktivieren Sie das Kontrollkästchen **PIN-Ablauf aktivieren** , um eine PIN-Ablaufdauer festzulegen. Wenn Sie diese Option nicht aktivieren, laufen PINs nie ab. In der Standardeinstellung ist für PINs kein Ablauf festgelegt.

10. Wenn Sie das Kontrollkästchen **PIN-Ablauf aktivieren** aktiviert haben, geben Sie unter **PIN-Ablauf nach (Tagen)** die Anzahl von Tagen ein, nach der PINs ablaufen.

11. Geben Sie unter **PIN-Verlaufszähler** die Anzahl von PINs ein, die ein Benutzer erstellen muss, bevor eine PIN erneut verwendet werden kann. In der Standardeinstellung können Benutzer ihre PINs erneut verwenden.

12. Aktivieren Sie das Kontrollkästchen **Allgemeine Muster zulassen** , um allgemeine Muster in PINs zuzulassen, beispielsweise aufeinanderfolgende und wiederholte Zahlen. Wenn Sie diese Option nicht aktivieren, sind nur komplexe Ziffernmuster zulässig. In der Standardeinstellung dürfen nur komplexe Ziffernmuster verwendet werden.
    

    > [!IMPORTANT]
    > Es wird empfohlen, die Verwendung gängiger Muster nicht zuzulassen.



13. Klicken Sie auf **Commit** .

## So ändern Sie eine PIN-Richtlinie auf Benutzer- oder Standortebene

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer des Netzwerks an, in dem Sie Lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **PIN-Richtlinie** .

4.  Klicken Sie auf der Seite **PIN-Richtlinie** auf die PIN-Richtlinie, die Sie ändern möchten. Klicken Sie dann auf **Bearbeiten** und anschließend auf **Details einblenden** .

5.  Ändern Sie im Abschnitt **PIN-Richtlinie bearbeiten** eine beliebige der Richtlinieneinstellungen. Hiervon ausgenommen ist der Richtlinienname, dieser kann nicht geändert werden.

6.  Klicken Sie auf **Commit** .

