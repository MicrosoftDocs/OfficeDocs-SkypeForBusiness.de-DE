---
title: Löschen einer Ortungsrichtlinie
TOCTitle: Löschen einer Ortungsrichtlinie
ms:assetid: 8ca9ba10-f45f-435a-b39c-519d251e9085
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688125(v=OCS.15)
ms:contentKeyID: 49890829
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen einer Ortungsrichtlinie

 

_**Letztes Änderungsdatum des Themas:** 2012-10-10_

Sie können die Ortungsrichtlinie in Lync Server 2013 verwenden, um die Einstellungen im Zusammenhang mit der Funktion "9-1-1 (erweitert) (E9-1-1)" und den Standorteinstellungen für Benutzer oder Kontakte zuzuweisen. Die Ortungsrichtlinie ermittelt, ob E9-1-1 für einen Benutzer aktiviert ist, und sie legt ggf. das Verhalten eines Notrufs fest. Sie können mit der Ortungsrichtlinie beispielsweise definieren, welche Nummer als Notrufnummer betrachtet wird (z. B. 911 in den Vereinigten Staaten), ob die Abteilung für Unternehmenssicherheit automatisch benachrichtigt und wie der Anruf weitergeleitet werden soll.

Sie können Ortungsrichtlinien in der Systemsteuerung für Lync Server 2013 über die Gruppe **Netzwerkkonfiguration** konfigurieren. In Lync Server-Systemsteuerung können Ortungsrichtlinien angezeigt, erstellt, geändert und gelöscht werden. Gehen Sie wie folgt vor, um eine Ortungsrichtlinie zu löschen. Ausführliche Informationen zum Erstellen oder Ändern von Ortungsrichtlinien finden Sie unter [Erstellen oder Ändern einer Ortungsrichtlinie](lync-server-2013-creating-or-modifying-a-location-policy.md).

## So löschen Sie eine Ortungsrichtlinie

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Ortungsrichtlinie**.

4.  Klicken Sie auf der Seite **Ortungsrichtlinie** auf die Ortungsrichtlinie, die gelöscht werden soll.
    

    > [!NOTE]
    > Sie können mehrere Ortungsrichtlinien in einem Arbeitsschritt löschen. Drücken Sie hierzu die STRG-TASTE, und wählen Sie bei gedrückter STRG-TASTE mehrere Richtlinien aus. Wenn Sie alle Richtlinien auswählen möchten, klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG>.



5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie auf **OK**.
    

    > [!IMPORTANT]
    > Die globale Ortungsrichtlinie kann nicht gelöscht werden. Beim Versuch, die globale Richtlinie zu löschen, wird eine Warnmeldung angezeigt, und die Richtlinie wird auf die Standardwerte zurückgesetzt.



## Siehe auch

#### Aufgaben

[Erstellen oder Ändern einer Ortungsrichtlinie](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[Anzeigen von Informationen zu Ortungsrichtlinien](lync-server-2013-viewing-location-policy-information.md)

