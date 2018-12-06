---
title: Konfigurieren von Lync Server 2013 für die Verwendung der Microsoft Exchange Server 2013-Archivierung
TOCTitle: Konfigurieren von Lync Server 2013 für die Verwendung der Exchange Server 2013-Archivierung
ms:assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ679896(v=OCS.15)
ms:contentKeyID: 49890668
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Microsoft Lync Server 2013 für die Verwendung der Microsoft Exchange Server 2013-Archivierung

 

_**Letztes Änderungsdatum des Themas:** 2014-06-24_

Administratoren können Chat- und Webkonferenzaufzeichnungen mithilfe von Microsoft Lync Server 2013 im Microsoft Exchange Server 2013-Postfach eines Benutzers anstatt in einer SQL Server-Datenbank archivieren. Wenn Sie diese Option aktivieren, werden Aufzeichnungen in den Löschordner des Benutzerpostfachs geschrieben. Der Löschordner ist ein ausgeblendeter Ordner im Ordner **Wiederherstellbare Elemente** . Obwohl dieser Ordner für Endbenutzer nicht sichtbar ist, wird er von der Exchange-Suchmaschine indiziert und kann mithilfe der Exchange-Postfachsuche und/oder Microsoft SharePoint Server 2013 ermittelt werden. Da die Informationen mithilfe des Exchange-Features **Compliance-Archiv** (verantwortlich für die Archivierung von E-Mail und anderer Exchange-Kommunikation) im gleichen Ordner gespeichert werden, können Administratoren ein einzelnes Tool verwenden, um nach der gesamten archivierten elektronischen Kommunikation für einen Benutzer zu suchen.


> [!IMPORTANT]
> Um die Archivierung von Lync-Unterhaltungen vollständig zu deaktivieren, müssen Sie außerdem den Lync-Unterhaltungsverlauf aktivieren. Weitere Informationen hierzu finden Sie in den folgenden Themen: <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Verwalten der Archivierung von interner und externer Kommunikation in Lync Server 2013</A>, <A href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A> und <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A>.



Zum Archivieren der Aufzeichnungen in Exchange 2013 müssen Sie zunächst eine Server-zu-Server-Authentifizierung zwischen den beiden Servern konfigurieren. Nachdem die Server-zu-Server-Authentifizierung eingerichtet ist, können Sie in Microsoft Lync Server 2013 die folgenden Aufgaben ausführen (je nach Setup und Konfiguration müssen Sie ggf. nur einen Teil dieser Aufgaben ausführen):

1.  Aktivieren Sie die Exchange-Archivierung, indem Sie Ihre Lync Server-Archivierungskonfigurationseinstellungen ändern. Dieser Schritt ist für alle Bereitstellungen erforderlich.

2.  Aktivieren Sie die Archivierung der internen und/oder externen Kommunikation für Ihre Benutzer. Dieser Schritt ist für alle Bereitstellungen erforderlich.

3.  Konfigurieren Sie die Eigenschaft **ExchangeArchivingPolicy** für jeden Benutzer. Dieser Schritt ist nur erforderlich, wenn sich Lync Server und Exchange in verschiedenen Gesamtstrukturen befinden.

## Schritt 1: Aktivieren der Exchange-Archivierung

Die Archivierung in Lync Server wird hauptsächlich mithilfe der Archivierungskonfigurationseinstellungen verwaltet. Bei der Installation von Lync Server 2013 erhalten Sie automatisch eine einzelne, globale Auflistung dieser Einstellungen. (Administratoren können optional neue Auflistungen von Archivierungseinstellungen auf Standortebene erstellen). Standardmäßig ist weder die Archivierung noch die Exchange-Archivierung in den globalen Einstellungen aktiviert. Zur Verwendung der Exchange-Archivierung müssen Administratoren sowohl die Eigenschaft **EnableArchiving** als auch die Eigenschaft **EnableExchangeArchiving** in diesen Konfigurationseinstellungen konfigurieren. Die Eigenschaft **EnableArchiving** kann auf einen von drei möglichen Werten festgelegt werden:

  - **None** . Die Archivierung ist deaktiviert. Dies ist der Standardwert. Wenn **EnableArchiving** auf **None** festgelegt ist, wird weder in der Lync Server-Archivierungsdatenbank noch in Exchange 2013 irgendetwas archiviert.

  - **ImOnly.** Nur Chattaufzeichnungen werden archiviert. Wenn die Exchange-Archivierung aktiviert ist, werden diese Aufzeichnungen in Exchange 2013 archiviert. Wenn die Exchange-Archivierung deaktiviert ist, werden diese Aufzeichnungen in Lync Server archiviert.

  - **ImAndWebConf** . Sowohl Chat- als auch Webkonferenzaufzeichnungen werden archiviert. Wenn die Exchange-Archivierung aktiviert ist, werden diese Aufzeichnungen in Exchange 2013 archiviert. Wenn die Exchange-Archivierung deaktiviert ist, werden diese Aufzeichnungen in Lync Server archiviert.

Die Eigenschaft **EnableExchangeArchiving** ist ein boolescher Wert: Legen Sie **EnableExchangeArchiving** auf **True** ( **$True** ) fest, um die Exchange-Archivierung zu aktivieren, oder legen Sie **EnableExchangeArchiving** auf **False** ( **$False** ) fest, um die Exchange-Archivierung zu deaktivieren. Mit diesem Befehl wird beispielsweise die Archivierung von Chataufzeichnungen und auch die Exchange-Archivierung aktiviert:

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

Verwenden Sie zum Deaktivieren der Exchange-Archivierung einen ähnlichen Befehl wie den folgenden, um die Chatarchivierung zu aktivieren, aber die Archivierung in Exchange zu deaktivieren (d. h., Aufzeichnungen werden in Lync Server archiviert):

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False


> [!NOTE]
> Wenn die Eigenschaft <STRONG>EnableArchiving</STRONG> auf <STRONG>None</STRONG> gesetzt ist, werden in Lync Server überhaupt keine Chat- und Webkonferenzaufzeichnungen archiviert. In diesem Fall ignoriert der Server einfach den für <STRONG>EnableExchangeArchiving</STRONG> konfigurierten Wert.



Die Exchange-Archivierung kann auch mithilfe der Lync Server-Systemsteuerung aktiviert (oder deaktiviert) werden. Führen Sie hierzu das folgende Verfahren aus:

1.  Klicken Sie in der Systemsteuerung auf **Überwachung und Archivierung** und dann auf **Archivierungskonfiguration** .

2.  Doppelklicken Sie auf der Registerkarte **Archivierungskonfiguration** auf die zu ändernde Auflistung von Archivierungseinstellungen (z. B. auf die Auflistung **Global** ).

3.  Klicken Sie im Bereich **Archivierungseinstellung bearbeiten** auf die Dropdownliste **Archivierungseinstellung** , und wählen Sie entweder **Chatsitzungen archivieren** (um nur Chatsitzungen zu archivieren) oder **Chat- und Webkonferenzsitzungen archivieren** (um sowohl Chat- als auch Webkonferenzsitzungen zu archivieren) aus.

4.  Aktivieren Sie nach Auswahl der zu archivierenden Elemente das Kontrollkästchen **Exchange Server-Integration** , um die Exchange-Archivierung zu aktivieren. Deaktivieren Sie dieses Kontrollkästchen, um die Exchange-Archivierung zu deaktivieren.


> [!NOTE]
> Das Kontrollkästchen <STRONG>Exchange Server-Integration</STRONG> ist nicht verfügbar, wenn <STRONG>Archivierungseinstellung</STRONG> auf <STRONG>Archivierung deaktivieren</STRONG> festgelegt ist. Sie müssen zuerst die Archivierung und dann die Exchange-Archivierung aktivieren.



Wenn sich Lync Server 2013 und Exchange 2013 in derselben Gesamtstruktur befinden, wird die Archivierung für einzelne Benutzer (oder zumindest für Benutzer, die E-Mail-Konten in Exchange 2013 besitzen) mithilfe von Exchange Compliance-Archive-Richtlinien verwaltet. Wenn Ihre Benutzer in einer vorherigen Version von Exchange verwaltet werden, wird die Archivierung für diese Benutzer mithilfe von Lync Server-Archivierungsrichtlinien verwaltet. Beachten Sie, dass nur für Benutzer mit einem Exchange 2013-Konto die Lync-Aufzeichnungen in Exchange archiviert werden können.

Befinden sich Lync Server 2013 und Exchange 2013 in verschiedenen Gesamtstrukturen, wird die Archivierung für einzelne Benutzer verwaltet, indem die Eigenschaft **ExchangeArchivingPolicy** für jedes einzelne Benutzerkonto konfiguriert wird. Weitere Informationen finden Sie in Schritt 3.

## Schritt 2: Aktivieren der Archivierung der internen und/oder externen Kommunikation

Nachdem Sie die Archivierung (und Exchange-Archivierung) aktiviert haben, müssen Sie die entsprechenden Archivierungsrichtlinien ändern, um sicherzustellen, dass Benutzersitzungen tatsächlich archiviert werden. Beachten Sie, dass es nicht genügt, einfach die Archivierung zu aktivieren (Schritt 1), damit in Lync Server mit dem Archivieren von Chat- und Webkonferenzaufzeichnungen begonnen wird. Stattdessen müssen Sie mit Archivierungsrichtlinien die interne und/oder externe Archivierung aktivieren. Bei der Installation von Lync Server 2013 müssen Sie auch eine einzelne, globale Archivierungsrichtlinie installieren, die zwei Eigenschaften enthält:

  - **ArchiveInternal** Ist diese Eigenschaft auf **True** ( **$True** ) gesetzt, werden interne Kommunikationssitzungen archiviert, an der nur Benutzer in der Organisation beteiligt sind, die ein Active Directory-Konto besitzen.

  - **ArchiveExternal** : Ist diese Eigenschaft auf **True** ( **$True** ) gesetzt, werden externe Kommunikationssitzungen archiviert (Sitzungen, an denen mindestens ein Benutzer beteiligt ist, der kein Active Directory-Konto in Ihrer Organisation besitzt).

Standardmäßig sind diese beiden Eigenschaftswerte auf **False** gesetzt. Das bedeutet, das weder interne noch externe Kommunikationssitzungen archiviert werden. Zum Ändern der globalen Richtlinie können Sie Lync Server-Verwaltungsshell und das Cmdlet **Set-CsArchivingPolicy** verwenden. Mit diesem Befehl wird sowohl die Archivierung von internen als auch externen Kommunikationssitzungen aktiviert:

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

Alternativ können Sie **New-CsArchivingPolicy** verwenden, um entweder auf Standort- oder auf Einzelbenutzerebene eine neue Richtlinie zu erstellen. Mit diesem Befehl wird z. B. eine neue Archivierungsrichtlinie auf Benutzerebene namens **RedmondArchivingPolicy** erstellt:

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

Wenn Sie eine Richtlinie auf Einzelbenutzerebene erstellen, müssen Sie diese Richtlinie den entsprechenden Benutzern zuweisen. Beispiel:

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

Archivierungseinstellungen können auch mithilfe der Lync Server-Systemsteuerung verwaltet werden. Klicken Sie in der Systemsteuerung auf **Überwachung und Archivierung** , und klicken Sie dann auf **Archivierungsrichtlinie** . Wenn Sie eine vorhandene Richtlinie ändern möchten, doppelklicken Sie auf die entsprechende Richtlinie (z. B. **Global** ), und aktivieren oder deaktivieren Sie dann im Bereich **Archivierungsrichtlinie bearbeiten** bei Bedarf das Kontrollkästchen **Interne Kommunikation archivieren** und **Externe Kommunikation archivieren** . Klicken Sie zum Erstellen einer neuen Richtlinie auf **Neu** , und aktivieren Sie dann entweder **Standortrichtlinie** oder **Benutzerrichtlinie** . Wenn Sie eine neue Benutzerrichtlinie erstellen, müssen Sie (über die Registerkarte **Benutzer** ) auf die entsprechenden Benutzerkonten zugreifen und diesen Benutzern die neue Richtlinie zuweisen.

## Schritt 3: Konfigurieren der Eigenschaft "ExchangeArchivingPolicy"

Wenn sich Lync Server 2013 und Exchange 2013 in verschiedenen Gesamtstrukturen befinden, genügt es nicht, einfach nur die Exchange-Archivierung in den Archivierungskonfigurationseinstellungen zu aktivieren. Dies allein bewirkt nämlich nicht, dass Chat- und Webkonferenzaufzeichnungen in Exchange archiviert werden. Stattdessen müssen Sie auch die Eigenschaft **ExchangeArchivingPolicy** für jedes der relevanten Lync Server-Benutzerkonten konfigurieren. Diese Eigenschaft kann auf einen von vier möglichen Werten festgelegt werden:

1.  **Uninitialized** . Zeigt an, dass die Archivierung auf den Compliance-Archiv-Einstellungen basiert, die für das Exchange-Postfach des Benutzers konfiguriert sind. Wenn das Compliance-Archiv nicht für das Postfach des Benutzer aktiviert wurde, werden die Chat- und Webkonferenzaufzeichnungen des Benutzers in Lync Server archiviert.

2.  **UseLyncArchivingPolicy** . Zeigt an, dass die Chat- und Webkonferenzaufzeichnungen des Benutzers in Lync Server anstatt in Exchange archiviert werden sollen.

3.  **NoArchiving** . Zeigt an, dass die Chat- und Webkonferenzaufzeichnungen des Benutzers überhaupt nicht archiviert werden sollten. Beachten Sie, dass diese Einstellung alle dem Benutzer zugewiesenen Lync Server-Archivierungsrichtlinien überschreibt.

4.  **ArchivingToExchange** . Zeigt an, dass die Chat- und Webkonferenzaufzeichnungen des Benutzers, unabhängig von den Compliance-Archive-Einstellungen, die dem Postfach des Benutzers zugewiesen wurden oder nicht, in Exchange archiviert werden sollen.

Um beispielsweise ein Benutzerkonto so zu konfigurieren, dass Chat- und Webkonferenzaufzeichnungen immer in Exchange archiviert werden, können Sie einen ähnlichen Befehl wie den folgenden an der Lync Server-Verwaltungsshell eingeben:

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

Wenn Sie dieselbe Archivierungsrichtlinie für eine Gruppe von Benutzern (z. B. alle Benutzer, die im angegebenen Registrierungsstellenpool verwaltet werden) festlegen möchten, können Sie einen ähnlichen Befehl wie den folgenden verwenden:

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

Sie müssen den Wert der Eigenschaft **ExchangeArchivingPolicy** mit der Lync Server-Verwaltungsshell (und Windows PowerShell) konfigurieren. Diese Eigenschaft wird nicht für Administratoren in der Lync Server-Systemsteuerung verfügbar gemacht.

Wenn Sie eine Liste aller Benutzer anzeigen möchten, denen eine bestimmte Archivierungsrichtlinie zugewiesen wurde, können Sie einen ähnlichen Befehl wie den folgenden verwenden. Der Befehl gibt den Active Directory-Anzeigenamen aller Benutzer zurück, für die die Eigenschaft **ExchangeArchivingPolicy** auf **Uninitialized** festgelegt ist:

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName

Entsprechend gibt dieser Befehl den Anzeigenamen aller Benutzer zurück, für die die Eigenschaft **ExchangeArchivingPolicy** auf **UseLyncArchivingPolicy** festgelegt ist:

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName

