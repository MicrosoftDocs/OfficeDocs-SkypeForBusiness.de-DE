---
title: Einrichten von Standortrichtlinien für die Archivierung
TOCTitle: Einrichten von Standortrichtlinien für die Archivierung
ms:assetid: dc2ea206-8b9c-44dd-a479-efb217593c89
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205325(v=OCS.15)
ms:contentKeyID: 49295617
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Einrichten von Standortrichtlinien für die Archivierung

 

_**Letztes Änderungsdatum des Themas:** 2012-10-09_

Die Archivierung können Sie für bestimmte Standorte aktivieren bzw. deaktivieren, indem Sie für jeden dieser Standorte eine Archivierungsrichtlinie erstellen und konfigurieren. Eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie, aber Benutzerrichtlinien haben Vorrang vor Standortrichtlinien. Archivierungsrichtlinien gelten nur, wenn Sie die Microsoft Exchange-Integration nicht verwenden, oder aber wenn Sie die Microsoft Exchange-Integration verwenden, aber einige Benutzer nicht in Exchange 2013 verwaltet werden und für ihre Postfächer "Compliance-Archiv" festgelegt wurde.

Ausführliche Informationen zur Funktionsweise von Archivierungsrichtlinien, einschließlich der Hierarchie für globale, Standort- und Benutzerrichtlinien, finden Sie unter [Funktionsweise der Archivierung in Lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungs-, Bereitstellungs- oder Betriebsdokumentation.


> [!NOTE]
> Wenn Sie die Microsoft Exchange-Integration für Ihre Bereitstellung aktivieren, bestimmen Compliance-Archiv-Richtlinien von Exchange, ob die Archivierung für die Benutzer aktiviert wird, die in Exchange 2013 verwaltet werden und für deren Postfächer "Compliance-Archiv" festgelegt wurde. Ausführliche Informationen hierzu finden Sie unter <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Einrichten von Richtlinien für die Archivierung beim Verwenden von Exchange Server-Integration</A> in der Bereitstellungsdokumentation.<BR>Sie sollten alle entsprechenden Optionen für die Archivierungskonfigurationen angeben, bevor Sie die Archivierung interner oder externer Kommunikation in den Archivierungsrichtlinien aktivieren. Ausführliche Informationen hierzu finden Sie unter <A href="lync-server-2013-configuring-archiving-options.md">Konfigurieren von Archivierungsoptionen</A> in der Bereitstellungsdokumentation.



## So erstellen Sie eine Archivierungsrichtlinie für einen Standort

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Systemsteuerung für Lync Server 2013 zu öffnen.

3.  Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.
    
    Ausführliche Informationen zur Funktionsweise von Archivierungsrichtlinien, einschließlich der Hierarchie für globale, Standort- und Benutzerrichtlinien, finden Sie unter [Funktionsweise der Archivierung in Lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungs-, Bereitstellungs- oder Betriebsdokumentation.

4.  Klicken Sie auf **Neu** und anschließend auf **Standortrichtlinie**.

5.  Klicken Sie im Dialogfeld **Standort auswählen** auf den Standort, auf den die Richtlinie angewendet werden soll.

6.  Führen Sie unter **Neue Archivierungsrichtlinie** die folgenden Aktionen aus:
    
      - Geben Sie im Feld **Name** den Namen für die Standortrichtlinie an.
    
      - Geben Sie im Feld **Beschreibung** Informationen zum Verwendungszweck der Standortrichtlinie an (z. B. Standortrichtlinie für Redmond).
    
      - Aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**, um die Archivierung der internen Kommunikation für den angegebenen Standort zu aktivieren oder zu deaktivieren.
    
      - Aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**, um die Archivierung der externen Kommunikation für den angegebenen Standort zu aktivieren oder zu deaktivieren.

7.  Klicken Sie auf **Commit ausführen**.

