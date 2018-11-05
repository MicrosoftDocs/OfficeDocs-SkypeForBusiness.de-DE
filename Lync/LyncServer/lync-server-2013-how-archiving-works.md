---
title: Funktionsweise der Archivierung in Lync Server 2013
TOCTitle: Funktionsweise der Archivierung in Lync Server 2013
ms:assetid: 536a52a9-cfb7-4392-9620-ffc5b319b31b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204900(v=OCS.15)
ms:contentKeyID: 49294018
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Funktionsweise der Archivierung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-02-04_

Die Optionen der Archivierung von Lync Server 2013 unterstützten Sie bei der Erfüllung Ihrer Kompatibilitätsanforderungen. Sie sollten sich Gedanken über folgende Punkte machen, um die einzelnen Optionen so zu implementieren und zu verwalten, dass die Anforderungen Ihrer Organisation möglichst optimal erfüllt werden:

  - Welche Informationen können archiviert werden?

  - Wie kann die Archivierung in der Bereitstellung aktiviert bzw. deaktiviert werden?

  - Welche Archivierungsoptionen können konfiguriert werden, um die Implementierung der Archivierung zu steuern?

## Welche Informationen können archiviert werden?

Folgende Arten von Inhalt können archiviert werden:

  - Peer-zu-Peer-Chatnachrichten

  - Konferenzen (Besprechungen), die Teil von Chatnachrichtensitzungen mit mehreren Teilnehmern sind

  - Konferenzinhalte, einschließlich hochgeladener Inhalte (z. B. Handzettel) sowie ereignisbezogener Inhalte (z. B. Beitritt zu/Verlassen einer Konferenz, Hochladen/Freigeben von Inhalten oder Änderungen in der Sichtbarkeit)

  - Whiteboards und Abstimmungen für alle Teilnehmer im Rahmen einer Konferenz

Die folgenden Arten von Inhalt können nicht archiviert werden:

  - Peer-to-Peer-Dateiübertragungen

  - Audio-/Videoinhalte für Peer-zu-Peer-Chatnachrichten und -konferenzen

  - Desktop- und Anwendungsfreigaben für Peer-zu-Peer-Chatnachrichten und -konferenzen

Darüber hinaus werden von Lync Server keine Beständiger Chat-Unterhaltungen archiviert. Wenn Sie Beständiger Chat-Unterhaltungen archivieren möchten, müssen Sie den Kompatibilitätsdienst aktivieren und konfigurieren. Der Kompatibilitätsdienst, der mit Microsoft Lync Server 2013, Server für beständigen Chat bereitgestellt werden kann. Nähere Informationen finden Sie in der Planungsdokumentation unter [Planen für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).

## Wie kann ich mit der Archivierung beginnen?

Die Archivierung wird bei der Bereitstellung des Servers automatisch auf jedem Front-End-Server installiert. Zum Verwenden der Archivierung müssen Sie sie jedoch zunächst konfigurieren. Die Konfiguration der Archivierung ist dabei abhängig von Ihrer Bereitstellung:

  - **Archivierung mit Microsoft Exchange-Integration.** Wenn Sie über Benutzer verfügen, die in Exchange 2013 verwaltet werden und deren Postfächer im Compliance-Archiv abgelegt wurden, können Sie diese Option auswählen, um den Lync Server 2013-Speicher in den Exchange-Speicher zu integrieren. Wenn Sie die Microsoft Exchange-Integrationsoption auswählen, können Sie die Archivierung der Lync Server 2013-Daten für diese Benutzer mit Exchange 2013 kontrollieren.

  - **Archivierung mit Lync Server-Archivierungsdatenbanken.** Wenn Sie über Benutzer verfügen, die nicht in Exchange 2013 verwaltet werden oder deren Postfächer nicht im Compliance-Archiv abgelegt wurden, oder wenn Sie die Microsoft Exchange-Integration nicht oder nicht für alle Benutzer in Ihrer Bereitstellung verwenden möchten, können Sie Lync Server-Archivierungsdatenbanken mit SQL Server bereitstellen, um die Archivierungsdaten für diese Benutzer zu speichern. In diesem Fall bestimmen die Richtlinien und Konfigurationen für die Lync Server 2013-Archivierung, ob die Archivierung aktiviert und wie sie implementiert wird. Wenn Sie Lync Server 2013 verwenden möchten, müssen Sie die entsprechende SQL Server-Datenbank Ihrer Topologie hinzufügen und die Topologie veröffentlichen.

## Einrichten der Archivierung bei Verwendung der Microsoft Exchange-Integration

Wenn Ihre Benutzer in Exchange 2013 verwaltet werden und ihre Postfächer im Compliance-Archiv abgelegt wurden, können Sie die **Microsoft Exchange-Integrationoption** (wie im weiteren Verlauf dieses Abschnitts beschrieben) auswählen, um Lync Server 2013 für diese Benutzer zu archivieren. Anschließend können Sie die Archivierung für diese Benutzer durch Angeben von Exchange-Richtlinien und -Einstellungen für das Compliance-Archiv kontrollieren. Darüber hinaus können Sie mithilfe von Lync Server-Konfigurationen Folgendes steuern:

  - Zu archivierende Elemente (Chatnachrichten, Konferenzen oder beides)

  - Implementierung des kritischen Modus für Ihre Lync Server-Bereitstellung

  - Auswahl der Microsoft Exchange-Integrationsoption zum Speichern von archivierten Daten in Exchange 2013

Diese Konfigurationsoptionen für die Lync Server 2013-Archivierung werden im weiteren Verlauf dieses Abschnitts beschrieben. Informationen zum Konfigurieren der Exchange-Richtlinien und -Einstellungen für das Compliance-Archiv zur Unterstützung der Archivierung finden Sie in der Exchange 2013-Produktdokumentation.

## Einrichten der Archivierung bei Verwendung des Archivierungsdatenbankspeichers von Lync Server

Wenn Sie Daten für Benutzer in Ihrer Bereitstellung mit Lync Server-Archivierungsdatenbanken (in SQL Server-Datenbanken) archivieren möchten, können Sie Lync Server-Archivierungsrichtlinien konfigurieren, um die Archivierung für diese Benutzer zu aktivieren bzw. zu deaktivieren. In jeder Richtlinie können Sie die Archivierung für eines oder beide der folgenden Elemente aktivieren bzw. deaktivieren:

  - Interne Kommunikation

  - Externe Kommunikation

In der Standardeinstellung ist weder die Archivierung für die interne Kommunikation noch die Archivierung für die externe Kommunikation in den Lync Server-Archivierungsrichtlinien aktiviert. Sie können die Kommunikation mit Systemsteuerung für Lync Server 2013 oder mithilfe von Cmdlets in der Verwaltungsshell für Lync Server 2013 aktivieren bzw. deaktivieren.

Lync Server 2013-Archivierungsrichtlinien beinhalten folgende Richtlinien:

  - **Globale Archivierungsrichtlinie**. Dies ist die Standardarchivierungsrichtlinie. Sie wirkt sich auf die gesamte Bereitstellung aus. Die Richtlinie wird erstellt, wenn Sie Lync Server 2013 bereitstellen. In der Standardeinstellung ist weder die Archivierung für die interne Kommunikation noch die Archivierung für die externe Kommunikation aktiviert. Diese Richtlinie kann nicht gelöscht werden. Wenn Sie diese Option löschen, wird die globale Richtlinie auf die Standardeinstellungen zurückgesetzt.

  - **Standortarchivierungsrichtlinie**. Sie können auch die Archivierung für einen oder mehrere Standorte aktivieren oder deaktivieren. Dazu erstellen und konfigurieren Sie eine Archivierungsrichtlinie auf Standortebene für den bzw. die betreffenden Standorte. Wenn Sie eine Archivierungsrichtlinie auf Standortebene erstellen, ist die Archivierung zunächst deaktiviert. Alle Archivierungsrichtlinien auf Standortebene, die Sie erstellen, können auch wieder gelöscht werden. Eine Archivierungsrichtlinie auf Standortebene überschreibt die globale Richtlinie, allerdings nur für den in der Richtlinie angegebenen Standort. Wenn Sie beispielsweise die Archivierung für die interne und für die externe Kommunikation in Ihrer globalen Richtlinie aktivieren und eine Standortrichtlinie erstellen, in der die Archivierung für die externe Kommunikation deaktiviert ist, wird an diesem Standort nur die interne Kommunikation archiviert.

  - **Benutzerarchivierungsrichtlinie**. Sie können die Archivierung auch für bestimmte Benutzer oder Benutzergruppen aktivieren bzw. deaktivieren. Dazu erstellen, konfigurieren oder wenden Sie eine Archivierungsrichtlinie für die angegebenen Benutzer oder Benutzergruppen an. Wenn Sie eine Archivierungsrichtlinie auf Benutzerebene erstellen, ist die Archivierung standardmäßig nicht aktiviert. Alle Archivierungsrichtlinien auf Benutzerebene, die Sie erstellen, können auch wieder gelöscht werden. Außerdem können Sie die Benutzer oder Benutzergruppen ändern, auf die sich eine Archivierungsrichtlinie auswirkt. Die globale Richtlinie und alle Richtlinien auf Standortebene werden durch eine Archivierungsrichtlinie auf Benutzerebene überschrieben. Dies gilt jedoch nur für die Benutzer, die von der Richtlinie betroffen sind. Angenommen, Sie deaktivieren die Archivierung für die interne und für die externe Kommunikation in Ihrer globalen Richtlinie. Ferner erstellen Sie eine Richtlinie auf Standortebene, in der die Archivierung für die interne und für die externe Kommunikation aktiviert ist. Abschließend erstellen Sie eine Richtlinie auf Benutzerebene, in der Sie die Archivierung für die externe Kommunikation deaktivieren. In diesem Fall werden die externe und die interne Kommunikation für alle Standortbenutzer mit Ausnahme der Benutzer archiviert, auf die die Richtlinie auf Benutzerebene angewendet wird: Für diese Benutzer wird nur die interne Kommunikation archiviert.

Nähere Informationen zum erstmaligen Einrichten von Archivierungsrichtlinien bei der Bereitstellung der Archivierung finden Sie in der Bereitstellungsdokumentation unter [Konfigurieren und Zuweisen von Archivierungsrichtlinien](lync-server-2013-configuring-and-assigning-archiving-policies.md). Nähere Informationen zum Aktivieren und Deaktivieren der Archivierung der Kommunikation nach der Bereitstellung mithilfe von Richtlinien finden Sie in der Betriebsdokumentation unter [Verwalten der Archivierung von interner und externer Kommunikation in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md).


> [!NOTE]
> Wenn Sie sowohl Lync Server 2013-Archivierungsdatenbanken als auch die Microsoft Exchange-Integration implementieren, werden die Lync Server-Archivierungsrichtlinien durch die Exchange 2013-Richtlinien überschrieben. Dies gilt jedoch nur für Benutzer, die in Exchange 2013 verwaltet werden und deren Postfächer im Compliance-Archiv abgelegt wurden. Die Lync-Archivierung ist ausschließlich von der Microsoft Exchange-Richtlinie für die Compliance-Archivierung abhängig.



## Welche Optionen stehen für die Konfiguration der Archivierung zur Verfügung?

Neben der Verwendung von Richtlinien und dem Aktivieren und Deaktivieren der Archivierung stehen Ihnen weitere Archivierungsoptionen zur Verfügung. Sie können diese Optionen für die gesamte Bereitstellung oder für bestimmte Standorte und Pools konfigurieren. In aller Regel werden die Archivierungsoptionen über mindestens eine einschlägige Konfiguration in Systemsteuerung für Lync Server 2013 gesteuert. Sie können jedoch auch eine weitere Option nutzen, die nur mit Verwaltungsshell für Lync Server 2013 konfiguriert werden kann.

## Konfigurationsoptionen für die Archivierung in der Systemsteuerung von Lync Server 2013

Jede Archivierungskonfiguration beinhaltet folgende Optionen:

Die Konfiguration auf globaler Ebene wird automatisch beim Bereitstellen der Archivierung erstellt. Sie kann angepasst, nicht jedoch gelöscht werden. Wenn Sie die Option zum Löschen der globalen Konfiguration auswählen, werden die Einstellungen auf die Standardwerte zurückgesetzt. Sie können mehrere Standort- und Poolkonfigurationen erstellen, die zusammen mit der globalen Konfiguration die Archivierungseinstellungen festlegen. Folgende Konfigurationsoptionen stehen für die globale Konfiguration sowie für die einzelnen Standort- und Poolkonfigurationen zur Verfügung:

  - Archivierung deaktivieren, Archivierung nur für Chatnachrichten aktivieren oder Archivierung für Chatnachrichten und Konferenzen aktivieren.

  - Kritischen Modus konfigurieren, um Chatnachrichten und Konferenzsitzungen bei Lync Server-Fehlern zu blockieren. Fehler können folgende Elemente betreffen:
    
      - **Chatnachrichten**. Es liegt ein Problem mit dem Lync Server-Speicherdienst vor. In diesem Fall werden Chatnachrichten für Benutzer blockiert, für die die Archivierung aktiviert wurde.
    
      - **Konferenzen**. Fehler können eine nicht verfügbare Dateifreigabe oder ein Problem mit dem Speicherdienst sein. In diesem Fall werden aktiven Konferenzen, die beim Auftreten des Fehlers im Pool gehostet werden, in den eingeschränkten Modus umgeschaltet, und neue Konferenzen können nicht aktiviert werden.
    
    Chatnachrichten und Konferenzen werden nach dem Beheben des Fehlers automatisch wiederhergestellt.

  - Speichern archivierter Daten mit Exchange 2013 unter Verwendung der Microsoft Exchange Server 2013-Integration anstelle der Einrichtung separater SQL Server-Datenbanken für das Speichern von Lync Server 2013-Archivierungsdaten.

  - Optionen zum Löschen der archivierten Daten konfigurieren. Dabei muss auch angegeben werden, zu welchem Zeitpunkt archivierte Daten gelöscht werden sollen:
    
      - Nach einer bestimmten Anzahl von Tagen
    
      - Nach dem Exportieren der archivierten Daten (einschließlich der Daten, die nach Exchange hochgeladen wurden, wenn die Microsoft Exchange-Integration aktiviert ist).
    

    > [!NOTE]
    > Wenn Sie die Microsoft Exchange-Integration aktivieren, wird das Löschen von Daten für Benutzer, die in Exchange 2013 verwaltet werden, einschließlich der zugehörigen Postfächer im Compliance-Archiv, durch Exchange gesteuert. Die einzige Qualifizierung betrifft Konferenzdateien, die in der Dateifreigabe von Lync Server gespeichert sind. Wenn Sie die Option zum Löschen von Daten nach dem Exportieren auswählen, werden diese Dateien erst gelöscht, wenn sie exportiert (nach Exchange hochgeladen) wurden. Wenn Sie eine maximale Anzahl von Tagen für die Archivierung der Daten angegeben haben, werden die Daten nach Ablauf dieser Zeit gelöscht.



Die Archivierungsoptionen sind standardmäßig nicht aktiviert. Sie können die Archivierungskombination mit Systemsteuerung für Lync Server 2013 verwalten.

Folgende Archivierungskonfigurationen können angegeben werden:

  - **Konfiguration für die globale Archivierung**. Dies ist die Standardkonfiguration für die Archivierung. Sie wirkt sich auf die gesamte Bereitstellung aus und wird bei der Bereitstellung von Lync Server 2013 erstellt. Die Archivierung ist dabei standardmäßig nicht aktiviert. Sie können die globale Konfiguration bearbeiten, jedoch nicht löschen. Wenn Sie für die Konfiguration die Option zum Löschen auswählen, wird die globale Konfiguration auf die Standardeinstellungen zurückgesetzt.

  - **Konfiguration für die Standortarchivierung**. Sie können die Archivierung auch für einen oder mehrere spezifische Standorte konfigurieren. Dazu erstellen und konfigurieren Sie eine Archivierungskonfiguration auf Standortebene für einen einzelnen Standort. Archivierungskonfigurationen auf Standortebene sind standardmäßig nicht vorhanden, sondern müssen explizit erstellt werden. Sie können jede Archivierungskonfiguration auf Standortebene bearbeiten oder löschen. Eine Archivierungskonfiguration auf Standortebene überschreibt die globale Konfiguration. Dies gilt jedoch nur für den in der Konfiguration auf Standortebene angegebenen Standort. Wenn Sie beispielsweise in der globalen Konfiguration die Archivierung nur für Chatnachrichten aktiviert haben und eine Standortkonfiguration erstellen, in der zusätzlich die Archivierung für Konferenzen aktiviert wird, werden Konferenzen nur für den Standort, jedoch nicht für die übrigen Teile der Organisation archiviert.

  - **Konfiguration für die Poolarchivierung**. Sie können auch Archivierungseinstellungen für einen oder mehrere Pools angeben, indem Sie eine Konfiguration auf Poolebene für den jeweiligen Pool erstellen und anpassen. Archivierungskonfigurationen auf Poolebene sind standardmäßig nicht vorhanden, sondern müssen explizit erstellt werden. Sie können jede Archivierungskonfiguration auf Poolebene bearbeiten oder löschen. Eine Archivierungskonfiguration auf Poolebene überschreibt die globale Konfiguration sowie alle ggf. erstellten Archivierungskonfigurationen auf Standortebene. Angenommen, Sie haben die Archivierung nur für Chatnachrichten in Ihrer globalen Konfiguration aktiviert. Nun erstellen Sie eine Konfiguration auf Standortebene, in der Sie für diesen Standort sowohl die Archivierung für Chatnachrichten als auch die Archivierung für Konferenzen aktivieren. Anschließend erstellen Sie eine Konfiguration auf Poolebene, in der Sie die Archivierung nur für Chatnachrichten aktivieren. In diesem Fall wird die Kommunikation sowohl für Chatnachrichten als auch für Konferenzen archiviert, und zwar für alle Benutzer des Standorts, und zwar mit Ausnahme der Benutzer, die in dem Pool verwaltet werden, der in der Konfiguration auf Poolebene angegeben wurde. Für alle anderen Benutzer in der Organisation wird hingegen nur die Archivierung von Chatnachrichten aktiviert.

Nähere Informationen zum erstmaligen Einrichten von Archivierungsrichtlinien bei der Bereitstellung der Archivierung finden Sie in der Bereitstellungsdokumentation unter [Konfigurieren von Archivierungsoptionen](lync-server-2013-configuring-archiving-options.md). Nähere Informationen zum Aktivieren und Deaktivieren der Archivierung der Kommunikation nach der Bereitstellung mithilfe von Richtlinien finden Sie in der Betriebsdokumentation unter [Verwalten von Konfigurationsoptionen für die Archivierung in Lync Server 2013 für Ihre Organisation, Standorte und Pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md).

## Exklusive Archivierungsoptionen für Windows PowerShell

In Verwaltungsshell für Lync Server 2013 können Sie mit Cmdlets die Optionen implementieren, die in Systemsteuerung für Lync Server 2013 nicht verfügbar sind. Dazu gehören u. a.:

  - **Archivierung doppelter Nachrichten**. Nähere Informationen finden Sie im Betriebshandbuch unter [New-CsArchivingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsArchivingConfiguration) und unter [Set-CsArchivingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsArchivingConfiguration).

  - **Exportieren archivierter Daten**. Nähere Informationen finden Sie unter [Export-CsArchivingData](https://docs.microsoft.com/en-us/powershell/module/skype/Export-CsArchivingData)

## Wie kann ich auf archivierte Daten zugreifen?

Der Zugriff auf archivierte Daten ist abhängig davon, wo die Daten gespeichert wurden:

  - **Microsoft Exchange-Speicher**. Wenn Sie die Exchange-Integrationsoption auswählen, werden die Archivierungsinhalte für alle Benutzer, die in Exchange 2013 verwaltet werden (und deren Postfächer sich im Compliance-Archiv befinden), von Lync Server im Exchange 2013-Speicher abgelegt. Archivierte Daten werden im Ordner "Wiederherstellbare Elemente" im Postfach des jeweiligen Benutzers gespeichert. Dieser wird standardmäßig nicht angezeigt und kann nur von Benutzern mit der Rolle Exchange-**Discoveryverwaltung** durchsucht werden. Exchange ermöglicht nach der Bereitstellung zusammen mit SharePoint die Erkennung und Suche von Verbünden. Nähere Informationen zum Speichern und Erkennen von Daten in Exchange finden Sie in der Exchange 2013- und in der SharePoint-Dokumentation.

  - **Lync Server-Speicher**. Wenn Sie Lync Server 2013-Archivierungsdatenbanken zum Speichern von Lync Server-Daten eingerichtet haben, werden Archivierungsinhalte von Lync Server für alle Benutzer, die nicht in Exchange 2013 verwaltet werden (und deren Postfächer nicht im Compliance-Archiv abgelegt wurden), in den Lync Server-Archivierungsdatenbanken (SQL Server-Datenbanken) abgelegt. Diese Daten können nicht durchsucht werden. Es ist jedoch möglich, die Daten zu exportieren und die Exportformate mit anderen Tools zu durchsuchen. Nähere Informationen zum Exportieren von Daten, die in Archivierungsdatenbanken gespeichert sind, finden Sie in der Betriebsdokumentation unter [Exportieren von archivierten Daten von Lync Server 2013](lync-server-2013-exporting-archived-data.md).

Nähere Informationen zur gemeinsamen Verwendung von Lync Server 2013 und Exchange 2013 finden Sie in der Unterstützungsdokumentation unter [Unterstützung der Integration von Exchange Server und SharePoint in Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md).

