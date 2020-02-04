---
title: Konfigurieren von lync Server 2013 für die Verwendung von Microsoft Exchange Server 2013-Archivierung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use Exchange Server 2013 archiving
ms:assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ679896(v=OCS.15)
ms:contentKeyID: 49557731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b163b0ce3324455f8a80eca7be5c1423b302a3d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving"></a>Konfigurieren von Microsoft lync Server 2013 für die Verwendung von Microsoft Exchange Server 2013-Archivierung

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-06-24_

Microsoft lync Server 2013 bietet Administratoren die Möglichkeit, im Postfach des Microsoft Exchange Server 2013 des Benutzers anstelle einer SQL Server-Datenbank Instant Messaging-und Webkonferenz Protokolle zu archivieren. Wenn Sie diese Option aktivieren, werden Aufzeichnungen in den Löschordner des Benutzerpostfachs geschrieben. Der Löschordner ist ein ausgeblendeter Ordner im Ordner „Wiederherstellbare Elemente“. Obwohl dieser Ordner für Endbenutzer nicht sichtbar ist, wird der Ordner von der Exchange-Suchmaschine indiziert und kann mithilfe der Exchange-Postfachsuche und/oder Microsoft SharePoint Server 2013 ermittelt werden. Da die Informationen im gleichen Ordner gespeichert sind, der von der Exchange-Funktion für in-situ-Speicher (für das Archivieren von e-Mails und anderer Exchange-Kommunikation) verwendet wird, können Administratoren ein einzelnes Tool verwenden, um nach der gesamten elektronischen Kommunikation zu suchen, die für eine archiviert wurde. Benutzer.

<div>


> [!IMPORTANT]  
> Um die Archivierung von lync-Unterhaltungen vollständig zu deaktivieren, müssen Sie auch das lync-Konversationsprotokoll deaktivieren. Weitere Informationen finden Sie unter den folgenden Themen: <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Verwalten der Archivierung interner und externer Kommunikation in lync Server 2013</A>, <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A>und <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">CsClientPolicy</A>.



</div>

Um Transkripte in Exchange 2013 zu archivieren, müssen Sie zunächst die Server-zu-Server-Authentifizierung zwischen den beiden Servern konfigurieren. Nachdem die Server-zu-Server-Authentifizierung eingerichtet ist, können Sie die folgenden Aufgaben in Microsoft lync Server 2013 ausführen (Beachten Sie, dass Sie – je nach Konfiguration und Konfiguration – möglicherweise nicht alle diese Aufgaben ausführen müssen):

1.  Aktivieren Sie die Exchange-Archivierung, indem Sie die Konfigurationseinstellungen ihrer lync Server-Archivierung ändern. Dieser Schritt ist für alle Bereitstellungen erforderlich.

2.  Aktivieren Sie die Archivierung der internen und/oder externen Kommunikation für Ihre Benutzer. Dieser Schritt ist für alle Bereitstellungen erforderlich.

3.  Konfigurieren Sie die Eigenschaft „ExchangeArchivingPolicy“ für jeden Benutzer. Dieser Schritt ist nur in lync Server erforderlich, und Exchange befindet sich in verschiedenen Gesamtstrukturen.

<div>

## <a name="step-1-enabling-exchange-archiving"></a>Schritt 1: Aktivieren der Exchange-Archivierung

Die Archivierung in lync Server wird hauptsächlich mithilfe der Archivierungs Konfigurationseinstellungen verwaltet. Wenn Sie lync Server 2013 installieren, erhalten Sie automatisch eine einzige globale Sammlung dieser Einstellungen. (Administratoren können optional neue Sammlungen von Archivierungseinstellungen im Website Bereich erstellen.) Standardmäßig ist die Archivierung in den globalen Einstellungen nicht aktiviert, und die Exchange-Archivierung ist in diesen Einstellungen nicht aktiviert. Um Exchange-Archivierungs Administratoren verwenden zu können, müssen die EnableArchiving-und die EnableExchangeArchiving-Eigenschaft in diesen Konfigurationseinstellungen konfiguriert werden. Die Eigenschaft „EnableArchiving“ kann auf einen von drei möglichen Werten festgelegt werden:

  - **Keine**. Die Archivierung ist deaktiviert. Dies ist der Standardwert. Wenn EnableArchiving auf None eingestellt ist, wird in ihrer lync Server-Archivierungsdatenbank oder in Exchange 2013 nichts archiviert.

  - Ist nicht **verfügbar.** Es werden nur Sofortnachrichten Abschriften archiviert. Wenn die Exchange-Archivierung aktiviert ist, werden diese Protokolle in Exchange 2013 archiviert. Wenn die Exchange-Archivierung deaktiviert ist, werden diese Protokolle auf lync Server archiviert.

  - **ImAndWebConf**. Sowohl Sofortnachrichten Protokolle als auch Webkonferenz-Transkripte werden archiviert. Wenn die Exchange-Archivierung aktiviert ist, werden diese Protokolle in Exchange 2013 archiviert. Wenn die Exchange-Archivierung deaktiviert ist, werden diese Protokolle auf lync Server archiviert.

Die EnableExchangeArchiving-Eigenschaft ist ein boolescher Wert: setzen Sie EnableExchangeArchiving auf true ($true), um die Exchange-Archivierung zu aktivieren oder EnableExchangeArchiving auf false festzulegen ($false), um die Exchange-Archivierung zu deaktivieren. Mit diesem Befehl können Sie beispielsweise die Archivierung von Sofortnachrichten Abschriften und die Exchange-Archivierung aktivieren:

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

Wenn Sie die Exchange-Archivierung deaktivieren möchten, verwenden Sie einen Befehl ähnlich der folgenden, der die Sofortnachrichten Archivierung ermöglicht, aber die Archivierung in Exchange deaktiviert (d. h., Transkripte werden auf dem lync-Server archiviert):

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False

<div>


> [!NOTE]  
> Wenn die EnableArchiving-Eigenschaft auf None eingestellt ist, werden von lync Server keine Sofortnachrichten und Webkonferenz-Transkripte archiviert. In diesem Fall ignoriert der Server einfach den für EnableExchangeArchiving konfigurierten Wert.



</div>

Die Exchange-Archivierung kann auch mithilfe der lync Server-Systemsteuerung aktiviert (oder deaktiviert) werden. Führen Sie hierzu das folgende Verfahren aus:

1.  Klicken Sie in der Systemsteuerung auf **Überwachung und Archivierung** und dann auf **Archivierungskonfiguration**.

2.  Doppelklicken Sie auf der Registerkarte **Archivierungskonfiguration** auf die zu ändernde Auflistung von Archivierungseinstellungen (z. B. auf die Auflistung **Global**).

3.  Klicken Sie im Bereich **Archivierungseinstellung bearbeiten** auf die Dropdownliste **Archivierungseinstellung** und wählen Sie entweder **Chatsitzungen archivieren** (um nur Chatsitzungen zu archivieren) oder **Chat- und Webkonferenzsitzungen archivieren** (um sowohl Chat- als auch Webkonferenzsitzungen zu archivieren).

4.  Nachdem Sie die zu archivierende Elemente ausgewählt haben, aktivieren Sie das Kontrollkästchen **Exchange-Server Integration** , um die Exchange-Archivierung zu aktivieren. Deaktivieren Sie dieses Kontrollkästchen, um die Exchange-Archivierung zu deaktivieren.

<div>


> [!NOTE]  
> Das Kontrollkästchen <STRONG>Exchange Server-Integration</STRONG> ist nicht verfügbar, wenn <STRONG>Archivierungseinstellung</STRONG> auf <STRONG>Archivierung deaktivieren</STRONG> festgelegt ist. Sie müssen zuerst die Archivierung aktivieren und dann die Exchange-Archivierung aktivieren.



</div>

Wenn sich lync Server 2013 und Exchange 2013 in derselben Gesamtstruktur befinden, wird die Archivierung für einzelne Benutzer (oder zumindest für Benutzer mit e-Mail-Konten in Exchange 2013) mithilfe von Exchange-in-situ-Speicherrichtlinien verwaltet. Wenn Sie über Benutzer verfügen, die in einer früheren Version von Exchange verwaltet werden, wird die Archivierung für diese Benutzer mithilfe von lync Server-Archivierungsrichtlinien verwaltet. Beachten Sie, dass nur Benutzer mit Konten in Exchange 2013 ihre lync-Transkripte in Exchange archivieren können.

Wenn sich lync Server 2013 und Exchange 2013 in verschiedenen Gesamtstrukturen befinden, wird die Archivierung für einzelne Benutzer durch Konfigurieren der ExchangeArchivingPolicy-Eigenschaft für jedes einzelne Benutzerkonto verwaltet. Weitere Informationen finden Sie in Schritt 3.

</div>

<div>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>Schritt 2: Aktivieren der Archivierung der internen und/oder externen Kommunikation

Nachdem Sie die Archivierung (und die Exchange-Archivierung) aktiviert haben, müssen Sie die entsprechenden Archivierungsrichtlinien ändern, um sicherzustellen, dass Benutzersitzungen tatsächlich archiviert werden. Beachten Sie, dass die Archivierung von Instant Messaging-und Webkonferenz-Transkripten nicht durch lync Server gestartet werden kann (Schritt 1). Stattdessen müssen Sie mit Archivierungsrichtlinien die interne und/oder externe Archivierung aktivieren. Wenn Sie lync Server 2013 installieren, installieren Sie auch eine einzige globale Archivierungsrichtlinie, die zwei Eigenschaften enthält:

  - **ArchiveInternal**: Ist diese Eigenschaft auf „True“ ($True) gesetzt, werden interne Kommunikationssitzungen archiviert, an denen nur Benutzer in der Organisation beteiligt sind, die ein Active Directory-Konto besitzen.

  - **ArchiveExternal**: Ist diese Eigenschaft auf „True“ ($True) gesetzt, werden externe Kommunikationssitzungen archiviert (Sitzungen, an denen mindestens ein Benutzer beteiligt ist, der kein Active Directory-Konto in Ihrer Organisation besitzt).

Standardmäßig sind beide Eigenschaftenwerte auf "false" festgelegt, was bedeutet, dass weder interne noch externe Kommunikationssitzungen archiviert werden. Zum Ändern der globalen Richtlinie können Sie die lync Server-Verwaltungsshell und das Cmdlet "Satz-CsArchivingPolicy" verwenden. Dieser Befehl ermöglicht die Archivierung interner und externer Kommunikationssitzungen:

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

Alternativ können Sie „New-CsArchivingPolicy“ verwenden, um entweder auf Standort- oder auf Einzelbenutzerebene eine neue Richtlinie zu erstellen. Mit diesem Befehl wird z. B. eine neue Archivierungsrichtlinie auf Benutzerebene namens „RedmondArchivingPolicy“ erstellt:

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

Wenn Sie eine Richtlinie auf Einzelbenutzerebene erstellen, müssen Sie diese Richtlinie den entsprechenden Benutzern zuweisen. Beispiel:

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

Archivierungsrichtlinien können auch mithilfe der lync Server-Systemsteuerung verwaltet werden. Klicken Sie in der Systemsteuerung auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**. Wenn Sie eine vorhandene Richtlinie ändern möchten, doppelklicken Sie auf die Richtlinie (z. b. Global), und aktivieren oder deaktivieren Sie dann im Bereich **Archivierungsrichtlinie bearbeiten** die Kontrollkästchen **interne Kommunikation** und **externe Kommunikation archivieren** nach Bedarf. Wenn Sie eine neue Archivierungsrichtlinie erstellen möchten, klicken Sie auf **neu** , und wählen Sie dann entweder **Website Richtlinie** oder **Benutzerrichtlinie**aus. Wenn Sie eine neue Benutzerrichtlinie erstellen, müssen Sie (über die Registerkarte „Benutzer“) auf die entsprechenden Benutzerkonten zugreifen und diesen Benutzern die neue Richtlinie zuweisen.

</div>

<div>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>Schritt 3: Konfigurieren der Eigenschaft "ExchangeArchivingPolicy"

Wenn sich lync Server 2013 und Exchange 2013 in unterschiedlichen Gesamtstrukturen befinden, reicht es nicht aus, die Exchange-Archivierung einfach in den Archivierungs Konfigurationseinstellungen zu aktivieren. Dadurch werden keine Instant Messaging-und Webkonferenz Protokolle in Exchange archiviert. Stattdessen müssen Sie auch die ExchangeArchivingPolicy-Eigenschaft für jedes der relevanten lync Server-Benutzerkonten konfigurieren. Diese Eigenschaft kann auf einen von vier möglichen Werten eingestellt werden:

1.  Uninitialized: Zeigt an, dass die Archivierung auf den Compliance-Archiv-Einstellungen basiert, die für das nm-exch-15-short-Postfach des Benutzers konfiguriert sind. Gibt an, dass die Archivierung auf den in-situ-Speicherungs Einstellungen basiert, die für das Exchange-Postfach des Benutzers konfiguriert sind. Wenn in-situ-Speicher für das Postfach des Benutzers nicht aktiviert wurde, werden die Nachrichten-und Webkonferenz Protokolle des Benutzers in lync Server archiviert.

2.  **UseLyncArchivingPolicy**. Gibt an, dass die Protokolle für Sofortnachrichten und Webkonferenzen des Benutzers in lync Server und nicht in Exchange archiviert werden sollen.

3.  **Noarchiving**. Gibt an, dass die Protokolle für Chatnachrichten und Webkonferenzen des Benutzers überhaupt nicht archiviert werden sollen. Beachten Sie, dass diese Einstellung alle lync Server-Archivierungsrichtlinien außer Kraft setzt, die dem Benutzer zugewiesen sind.

4.  **ArchivingToExchange**: zeigt an, dass die Chat- und Webkonferenzaufzeichnungen des Benutzers unabhängig von den Compliance-Archiv-Einstellungen, die ggf. Gibt an, dass die Protokolle des Benutzers für Sofortnachrichten und Webkonferenzen in Exchange unabhängig von den in-situ-Speicher-Einstellungen, die dem Postfach des Benutzers zugewiesen wurden (oder nicht), archiviert werden sollen.

Wenn Sie beispielsweise ein Benutzerkonto so konfigurieren möchten, dass Sofortnachrichten und Webkonferenz Protokolle immer in Exchange archiviert werden, können Sie einen ähnlichen Befehl wie den folgenden in der lync Server-Verwaltungsshell verwenden:

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

Wenn Sie dieselbe Archivierungsrichtlinie für eine Gruppe von Benutzern (z. B. alle Benutzer, die im angegebenen Registrierungsstellenpool verwaltet werden) festlegen möchten, können Sie einen ähnlichen Befehl wie den folgenden verwenden:

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

Beachten Sie, dass Sie die lync Server-Verwaltungsshell (und Windows PowerShell) verwenden müssen, um den Wert der ExchangeArchivingPolicy-Eigenschaft zu konfigurieren. Diese Eigenschaft wird für Administratoren in der lync Server-Systemsteuerung nicht verfügbar gemacht.

Wenn Sie eine Liste aller Benutzer anzeigen möchten, denen eine bestimmte Archivierungsrichtlinie zugewiesen wurde, können Sie einen ähnlichen Befehl wie den folgenden verwenden. Der Befehl gibt den Active Directory-Anzeigenamen aller Benutzer zurück, für die die Eigenschaft „ExchangeArchivingPolicy“ auf „Uninitialized“ festgelegt ist:

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName

Entsprechend gibt dieser Befehl den Anzeigenamen aller Benutzer zurück, für die die Eigenschaft „ExchangeArchivingPolicy“ auf „UseLyncArchivingPolicy“ festgelegt ist:

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName

</div>

</div>

<span> </span>

</div>

</div>

</div>

