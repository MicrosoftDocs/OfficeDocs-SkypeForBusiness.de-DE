---
title: Erstellen und Konfigurieren von Benutzerrichtlinien für die Archivierung in Lync Server
TOCTitle: Erstellen und Konfigurieren von Benutzerrichtlinien für die Archivierung in Lync Server
ms:assetid: 5af0e605-3563-4d6f-a3c6-511d204a3165
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204923(v=OCS.15)
ms:contentKeyID: 49294111
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen und Konfigurieren von Benutzerrichtlinien für die Archivierung in Lync Server

 

_**Letztes Änderungsdatum des Themas:** 2012-10-09_

Um die Archivierung für bestimmte Benutzer zu aktivieren oder zu deaktivieren, die in Lync Server verwaltet werden, müssen Sie zunächst eine Benutzerrichtlinie erstellen. Anschließend wenden Sie diese Richtlinie auf einen oder mehrere Benutzer oder Benutzergruppen an. Nähere Informationen über das Anwenden von Benutzerrichtlinien auf bestimmte Benutzer oder Benutzergruppen finden Sie in der Bereitstellungsdokumentation unter [Anwenden einer Lync Server-Archivierungsrichtlinie auf einen Benutzer](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md).

Nähere Informationen über die Funktionsweise der Archivierungsrichtlinien, einschließlich der Hierarchie der Richtlinien auf globaler Ebene sowie auf Standort- und Benutzerebene, finden Sie in der Planungs-, Bereitstellungs- oder Betriebsdokumentation unter [Funktionsweise der Archivierung in Lync Server 2013](lync-server-2013-how-archiving-works.md).


> [!NOTE]
> Wenn Sie die Microsoft Exchange-Integration für Ihre Bereitstellung aktivieren, bestimmen die Richtlinien für das Compliance-Archiv von Exchange, ob die Archivierung für Benutzer aktiviert wird, die in Exchange 2013 verwaltet werden und deren Postfächer sich im Compliance-Archiv befinden. Nähere Informationen finden Sie in der Bereitstellungsdokumentation unter <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Einrichten von Richtlinien für die Archivierung beim Verwenden von Exchange Server-Integration</A>.<BR>Konfigurieren Sie alle erforderlichen Optionen in den Archivierungseinstellungen, bevor Sie die Archivierung aktivieren. Nähere Informationen finden Sie in der Betriebsdokumentation unter <A href="lync-server-2013-configuring-archiving-options.md">Konfigurieren von Archivierungsoptionen</A>.



## So konfigurieren Sie eine Richtlinie für Benutzer unter Lync Server-Verwaltung

1.  Melden Sie sich mit einem Benutzerkonto, dem die CsArchivingAdministrator- oder die CsAdministrator-Rolle zugewiesen wurde, bei einem Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Systemsteuerung für Lync Server 2013 zu öffnen. Nähere Informationen über die verschiedenen Methoden zum Starten von Systemsteuerung für Lync Server 2013 finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.

4.  Klicken Sie auf **Neu** und auf **Benutzerrichtlinie**.

5.  Führen Sie unter **Neue Archivierungsrichtlinie** die folgenden Schritte aus:
    
      - Geben Sie im Feld **Name** den Namen der Benutzerrichtlinie an.
    
      - Machen Sie im Feld **Beschreibung** nähere Angaben zur Art der Benutzerrichtlinie (z. B. Benutzerrichtlinie für die Rechtsabteilung).
    
      - Um die Archivierung der internen Kommunikation für die Benutzerrichtlinie zu kontrollieren, aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**.
    
      - Um die Archivierung der externen Kommunikation für die Benutzerrichtlinie zu kontrollieren, aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**.

6.  Klicken Sie auf **Commit**.

Benutzerrichtlinien wirken sich nur auf Benutzer aus, denen eine solche Richtlinie zugewiesen wurde. Nähere Informationen zur Anwendung einer Benutzerrichtlinie auf bestimmte Benutzer finden Sie in der Bereitstellungsdokumentation unter [Anwenden einer Lync Server-Archivierungsrichtlinie auf einen Benutzer](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md).

