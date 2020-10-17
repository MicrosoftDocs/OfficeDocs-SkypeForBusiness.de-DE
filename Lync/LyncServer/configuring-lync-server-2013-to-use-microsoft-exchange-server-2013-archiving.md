---
title: Konfigurieren lync Server 2013 für die Verwendung Microsoft Exchange Server 2013 Archivierung
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
ms.openlocfilehash: b6f557c95b9bf706b3a38b51bdbea4fea156b314
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503162"
---
# <a name="configuring-microsoft-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving"></a>Konfigurieren Microsoft lync Server 2013 für die Verwendung Microsoft Exchange Server 2013 Archivierung

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-06-24_

Microsoft lync Server 2013 bietet Administratoren die Möglichkeit, Chatnachrichten und Webkonferenz-Transkripte im Microsoft Exchange Server 2013 Postfach eines Benutzers statt in einer SQL Server Datenbank zu archivieren. Wenn Sie diese Option aktivieren, werden Transkripte in den Ordner "Säuberungen" im Postfach des Benutzers geschrieben. Der Ordner "purges" ist ein ausgeblendeter Ordner, der im Ordner "refundable Items" gefunden wird. Obwohl dieser Ordner für Endbenutzer nicht sichtbar ist, wird der Ordner von der Exchange-Suchmaschine indiziert und kann mithilfe der Exchange-Postfachsuche und/oder Microsoft SharePoint Server 2013 ermittelt werden. Da Informationen in demselben Ordner gespeichert werden, der von der Exchange In-Place Hold-Funktion verwendet wird (zuständig für das Archivieren von e-Mails und anderen Exchange-Kommunikationen), können Administratoren ein einzelnes Tool verwenden, um nach der für einen Benutzer archivierten elektronischen Kommunikation zu suchen.

<div>


> [!IMPORTANT]  
> Um die Archivierung von lync-Unterhaltungen vollständig zu deaktivieren, müssen Sie auch den lync-Unterhaltungsverlauf deaktivieren. Weitere Informationen finden Sie in den folgenden Themen: <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Verwalten der Archivierung der internen und externen Kommunikation in lync Server 2013</A>, <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A>und <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">CsClientPolicy</A>.



</div>

Um Transkripte in Exchange 2013 archivieren zu können, müssen Sie zunächst die Server-zu-Server-Authentifizierung zwischen den beiden Servern konfigurieren. Nachdem die Server-zu-Server-Authentifizierung erfolgt ist, können Sie die folgenden Aufgaben in Microsoft lync Server 2013 ausführen (Beachten Sie, dass Sie in Abhängigkeit von ihrer Einrichtung und Konfiguration möglicherweise nicht alle diese Aufgaben ausführen müssen):

1.  Aktivieren Sie die Exchange-Archivierung durch Ändern ihrer lync Server Archivierungs Konfigurationseinstellungen. Dieser Schritt ist für alle Bereitstellungen erforderlich.

2.  Aktivieren Sie die Archivierung der internen und/oder externen Kommunikation für Ihre Benutzer. Dieser Schritt ist für alle Bereitstellungen erforderlich.

3.  Konfigurieren Sie die ExchangeArchivingPolicy-Eigenschaft für jeden Benutzer. Dieser Schritt ist nur in lync Server erforderlich, und Exchange befindet sich in unterschiedlichen Gesamtstrukturen.

<div>

## <a name="step-1-enabling-exchange-archiving"></a>Schritt 1: Aktivieren der Exchange-Archivierung

Die Archivierung in lync Server wird in erster Linie mithilfe der Archivierungs Konfigurationseinstellungen verwaltet. Wenn Sie lync Server 2013 installieren, erhalten Sie automatisch eine einzelne globale Auflistung dieser Einstellungen. (Administratoren können optional neue Sammlungen von Archivierungseinstellungen auf Standortebene erstellen.) Standardmäßig ist die Archivierung in den globalen Einstellungen nicht aktiviert, und die Exchange-Archivierung ist in diesen Einstellungen nicht aktiviert. Um Exchange-Archivierungs Administratoren verwenden zu können, müssen Sie die Eigenschaften Eigenschaft "enablearchiving und EnableExchangeArchiving in diesen Konfigurationseinstellungen konfigurieren. Die Eigenschaft "enablearchiving-Eigenschaft kann auf einen von drei möglichen Werten festgelegt werden:

  - **None**. Die Archivierung ist deaktiviert. Dies ist der Standardwert. Wenn Eigenschaft "enablearchiving auf None festgelegt ist, wird nichts in ihrer lync Server-Archivierungsdatenbank oder in Exchange 2013 archiviert.

  - Ist nicht **geschützt**. Nur Chattaufzeichnungen werden archiviert. Wenn die Exchange-Archivierung aktiviert ist, werden diese Transkripte in Exchange 2013 archiviert. Wenn die Exchange-Archivierung deaktiviert ist, werden diese Protokolle in lync Server archiviert.

  - **ImAndWebConf**. Sowohl Chat- als auch Webkonferenzaufzeichnungen werden archiviert. Wenn die Exchange-Archivierung aktiviert ist, werden diese Transkripte in Exchange 2013 archiviert. Wenn die Exchange-Archivierung deaktiviert ist, werden diese Protokolle in lync Server archiviert.

Die EnableExchangeArchiving-Eigenschaft ist ein boolescher Wert: Legen Sie EnableExchangeArchiving auf true ($true) fest, um die Exchange-Archivierung zu aktivieren oder EnableExchangeArchiving auf false festzulegen ($false), um die Exchange-Archivierung zu deaktivieren. Mit diesem Befehl können Sie beispielsweise die Archivierung von Instant Messaging-Transkripten und die Exchange-Archivierung aktivieren:

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

Um die Exchange-Archivierung zu deaktivieren, verwenden Sie einen Befehl wie den folgenden, der die Archivierung von Instant Messaging ermöglicht, aber die Archivierung in Exchange deaktiviert (mit anderen Worten, die Transkripte werden in lync Server archiviert):

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False

<div>


> [!NOTE]  
> Wenn die Eigenschaft "enablearchiving-Eigenschaft auf None festgelegt ist, werden lync Server keine Instant Messaging-und Webkonferenz-Transkripte archivieren. In diesem Fall ignoriert der Server einfach den Wert, der für EnableExchangeArchiving konfiguriert ist.



</div>

Die Exchange-Archivierung kann auch mithilfe der lync Server-Systemsteuerung aktiviert (oder deaktiviert) werden. Führen Sie hierzu das folgende Verfahren aus:

1.  Klicken Sie in der Systemsteuerung auf **Überwachung und Archivierung** und dann auf **Archivierungskonfiguration**.

2.  Doppelklicken Sie auf der Registerkarte **Archivierungskonfiguration** auf die zu ändernde Auflistung von Archivierungseinstellungen (z. B. auf die Auflistung **Global**).

3.  Klicken Sie im Bereich **Archivierungseinstellung bearbeiten** auf die Dropdownliste **Archivierungseinstellung**, und wählen Sie entweder**Chatsitzungen archivieren** (um nur Chatsitzungen zu archivieren) oder **Chat- und Webkonferenzsitzungen archivieren** (um sowohl Chat- als auch Webkonferenzsitzungen zu archivieren) aus.

4.  Nachdem Sie die zu archivierenden Elemente ausgewählt haben, aktivieren Sie das Kontrollkästchen **Exchange Server Integration** , um die Exchange-Archivierung zu aktivieren. Deaktivieren Sie dieses Kontrollkästchen, um die Exchange-Archivierung zu deaktivieren.

<div>


> [!NOTE]  
> Das Kontrollkästchen <STRONG>Exchange Server-Integration</STRONG> ist nicht verfügbar, wenn <STRONG>Archivierungseinstellung</STRONG> auf <STRONG>Archivierung deaktivieren</STRONG> festgelegt ist. Sie müssen zuerst die Archivierung aktivieren und dann die Exchange-Archivierung aktivieren.



</div>

Wenn sich lync Server 2013 und Exchange 2013 in derselben Gesamtstruktur befinden, wird die Archivierung für einzelne Benutzer (oder zumindest für Benutzer mit e-Mail-Konten in Exchange 2013) mithilfe von Exchange In-Place-Aufbewahrungsrichtlinien verwaltet. Wenn Sie über Benutzer verfügen, die in einer früheren Version von Exchange verwaltet werden, wird die Archivierung für diese Benutzer mithilfe lync Server Archivierungsrichtlinien verwaltet. Beachten Sie, dass nur Benutzer mit Konten in Exchange 2013 ihre lync-Transkripte in Exchange archivieren lassen können.

Wenn sich lync Server 2013 und Exchange 2013 in unterschiedlichen Gesamtstrukturen befinden, wird die Archivierung für einzelne Benutzer durch Konfigurieren der ExchangeArchivingPolicy-Eigenschaft für jedes einzelne Benutzerkonto verwaltet. Weitere Informationen finden Sie in Schritt 3.

</div>

<div>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>Schritt 2: Aktivieren der Archivierung der internen und/oder externen Kommunikation

Nachdem Sie die Archivierung (und die Exchange-Archivierung) aktiviert haben, müssen Sie die entsprechenden Archivierungsrichtlinien ändern, um sicherzustellen, dass die Benutzersitzungen tatsächlich archiviert werden. Beachten Sie, dass das einfache Aktivieren der Archivierung (Schritt 1) nicht dazu führt, dass lync Server mit der Archivierung von Instant Messaging-und Webkonferenz Abschriften beginnen. Stattdessen müssen Sie mit Archivierungsrichtlinien die interne und/oder externe Archivierung aktivieren. Wenn Sie lync Server 2013 installieren, installieren Sie auch eine einzelne, globale Archivierungsrichtlinie, die zwei Eigenschaften enthält:

  - **"Archiveinternal"**. Bei Festlegung auf "true" ($true) gibt an, dass interne Kommunikationssitzungen, an denen nur Benutzer mit Active Directory Konten in Ihrer Organisation beteiligt sind, archiviert werden.

  - **"Archiveexternal"**. Bei Festlegung auf "true" ($true) wird angegeben, dass interne Kommunikationssitzungen (Sitzungen mit mindestens einem Benutzer, der über kein Active Directory Konto in Ihrer Organisation verfügt) archiviert werden.

Standardmäßig sind beide Eigenschaftswerte auf false festgelegt, was bedeutet, dass weder interne noch externe Kommunikationssitzungen archiviert werden. Zum Ändern der globalen Richtlinie können Sie die lync Server-Verwaltungsshell und das Set-CsArchivingPolicy-Cmdlet verwenden. Mit diesem Befehl wird die Archivierung interner und externer Kommunikationssitzungen aktiviert:

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

Alternativ können Sie New-CsArchivingPolicy verwenden, um entweder auf Standort- oder auf Einzelbenutzerebene eine neue Richtlinie zu erstellen. Mit diesem Befehl wird z. B. eine neue Archivierungsrichtlinie auf Benutzerebene namens RedmondArchivingPolicy erstellt:

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

Wenn Sie eine Richtlinie auf Einzelbenutzerebene erstellen, müssen Sie diese Richtlinie den entsprechenden Benutzern zuweisen. Beispiel:

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

Archivierungsrichtlinien können auch mithilfe der lync Server-Systemsteuerung verwaltet werden. Klicken Sie in der Systemsteuerung auf **Überwachung und Archivierung** , und klicken Sie dann auf **Archivierungsrichtlinie**. Zum Ändern einer vorhandenen Richtlinie Doppelklicken Sie auf die Richtlinie (z. b. Global), und aktivieren oder deaktivieren Sie dann im Bereich **Archivierungsrichtlinie bearbeiten** die Kontrollkästchen **interne Kommunikation** und **externe Kommunikation archivieren** , falls erforderlich. Klicken Sie zum Erstellen einer neuen Archivierungsrichtlinie auf **neu** , und wählen Sie dann entweder **Standortrichtlinie** oder **Benutzerrichtlinie**aus. Wenn Sie eine neue Benutzerrichtlinie erstellen, müssen Sie auf die entsprechenden Benutzerkonten (auf der Registerkarte " **Benutzer** ") zugreifen und diesen Benutzern die neue Richtlinie zuweisen.

</div>

<div>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>Schritt 3: Konfigurieren der Eigenschaft "ExchangeArchivingPolicy"

Wenn sich lync Server 2013 und Exchange 2013 in unterschiedlichen Gesamtstrukturen befinden, genügt es nicht, die Exchange-Archivierung in den Archivierungs Konfigurationseinstellungen einfach zu aktivieren. Dadurch werden keine Instant Messaging-und Webkonferenz Protokolle in Exchange archiviert. Stattdessen müssen Sie auch die ExchangeArchivingPolicy-Eigenschaft für jedes der relevanten lync Server-Benutzerkonten konfigurieren. Diese Eigenschaft kann auf einen von vier möglichen Werten festgelegt werden:

1.  Initialisierten. Gibt an, dass die Archivierung auf den In-Place halten-Einstellungen basiert, die für das Exchange-Postfach des Benutzers konfiguriert sind; Wenn In-Place Haltestatus für das Postfach des Benutzers nicht aktiviert wurde, wird der Benutzer in lync Server über seine Messaging-und Webkonferenz Protokolle archiviert.

2.  **UseLyncArchivingPolicy**. Gibt an, dass die Protokolle für Chatnachrichten und Webkonferenzen des Benutzers in lync Server anstatt in Exchange archiviert werden sollen.

3.  **Noarchivierung**. Zeigt an, dass die Chat- und Webkonferenzaufzeichnungen des Benutzers überhaupt nicht archiviert werden sollten. Beachten Sie, dass diese Einstellung alle lync Server Archivierungsrichtlinien außer Kraft setzt, die dem Benutzer zugewiesen sind.

4.  **ArchivingToExchange**. Gibt an, dass die Protokolle für Sofortnachrichten und Webkonferenzen des Benutzers in Exchange archiviert werden sollen, unabhängig von den In-Place Aufbewahrungseinstellungen, die dem Postfach des Benutzers zugewiesen wurden (oder nicht).

Wenn Sie beispielsweise ein Benutzerkonto so konfigurieren möchten, dass Sofortnachrichten und Webkonferenz Protokolle immer in Exchange archiviert werden, können Sie einen Befehl wie den folgenden aus dem lync Server-Verwaltungsshell verwenden:

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

Wenn Sie dieselbe Archivierungsrichtlinie für eine Gruppe von Benutzern (z. B. alle Benutzer, die im angegebenen Registrierungsstellenpool verwaltet werden) festlegen möchten, können Sie einen ähnlichen Befehl wie den folgenden verwenden:

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

Beachten Sie, dass Sie die lync Server-Verwaltungsshell (und Windows PowerShell) verwenden müssen, um den Wert der ExchangeArchivingPolicy-Eigenschaft zu konfigurieren. Diese Eigenschaft wird für Administratoren im lync Server-Systemsteuerung nicht verfügbar gemacht.

Wenn Sie eine Liste aller Benutzer anzeigen möchten, denen eine bestimmte Archivierungsrichtlinie zugewiesen wurde, können Sie einen ähnlichen Befehl wie den folgenden verwenden. Der Befehl gibt den Active Directory-Anzeigenamen aller Benutzer zurück, für die die Eigenschaft ExchangeArchivingPolicy auf Uninitialized festgelegt ist:

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName

Entsprechend gibt dieser Befehl den Anzeigenamen aller Benutzer zurück, für die die Eigenschaft ExchangeArchivingPolicy auf UseLyncArchivingPolicy festgelegt ist:

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName

</div>

</div>

<span> </span>

</div>

</div>

</div>

