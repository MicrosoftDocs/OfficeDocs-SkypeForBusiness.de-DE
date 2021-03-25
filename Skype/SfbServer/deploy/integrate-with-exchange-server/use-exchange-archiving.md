---
title: Konfigurieren von Skype for Business Server für die Verwendung Exchange Server Archivierung
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
description: 'Zusammenfassung: Konfigurieren von Chat-Transkripts für Exchange Server 2016 oder Exchange Server 2013 und Skype for Business Server.'
ms.openlocfilehash: 43a57fc227f7fc0dbcb33b2ecb4808f3e9762ad6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120314"
---
# <a name="configure-skype-for-business-server-to-use-exchange-server-archiving"></a>Konfigurieren von Skype for Business Server für die Verwendung Exchange Server Archivierung

**Zusammenfassung:** Konfigurieren von Chat-Transkripts für Exchange Server 2016 oder Exchange Server 2013 und Skype for Business Server.

Skype for Business Server bietet Administratoren die Möglichkeit, Instant Messaging- und Webkonferenz-Transkripte in das Exchange Server 2016- oder Exchange Server 2013-Postfach eines Benutzers anstelle einer SQL Server-Datenbank zu archivieren. Wenn Sie diese Option aktivieren, werden Aufzeichnungen in den Ordner "Löschen" im Postfach des Benutzers geschrieben. Der Ordner "Löschen" ist ein ausgeblendeter Ordner im Ordner "Wiederherstellbare Elemente". Obwohl dieser Ordner für Endbenutzer nicht sichtbar ist, wird der Ordner von der Exchange-Suchmaschine indiziert und kann mithilfe der Exchange-Postfachsuche und/oder Microsoft SharePoint Server 2013 ermittelt werden. Da Informationen im gleichen Ordner gespeichert werden, der von der Exchange In-Place Hold-Funktion verwendet wird (zuständig für die Archivierung von E-Mails und andere Exchange-Kommunikation), können Administratoren ein einzelnes Tool verwenden, um nach der für einen Benutzer archivierten elektronischen Kommunikation zu suchen.

> [!IMPORTANT]
> Um die Unterhaltungsarchivierung vollständig zu deaktivieren, müssen Sie auch den Unterhaltungsverlauf deaktivieren. Weitere Informationen finden Sie in den folgenden Themen: Verwalten der Archivierung der internen und externen Kommunikation [in Skype for Business Server,](/previous-versions/office/lync-server-2013/lync-server-2013-managing-the-archiving-of-internal-and-external-communications) [New-CsClientPolicy](/powershell/module/skype/new-csclientpolicy?view=skype-ps)und [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps).

Zum Archivieren von Aufzeichnungen Exchange Server Sie zunächst die Server-zu-Server-Authentifizierung zwischen Skype for Business Server und Exchange Server. Nachdem die Server-zu-Server-Authentifizierung eingerichtet wurde, können Sie die folgenden Aufgaben in Skype for Business Server ausführen (beachten Sie, dass Sie je nach Einrichtung und Konfiguration möglicherweise nicht alle diese Aufgaben ausführen müssen):

1. Aktivieren Sie die Exchange-Archivierung, indem Sie Ihre Skype for Business Server-Archivierungskonfigurationseinstellungen ändern. Dieser Schritt ist für alle Bereitstellungen erforderlich.

2. Aktivieren Sie die Archivierung der internen und/oder externen Kommunikation für Ihre Benutzer. Dieser Schritt ist für alle Bereitstellungen erforderlich.

3. Konfigurieren Sie die ExchangeArchivingPolicy-Eigenschaft für jeden Benutzer. Dieser Schritt ist nur erforderlich, wenn sich Skype for Business Server und Exchange Server in verschiedenen Gesamtstrukturen befinden.

## <a name="step-1-enabling-exchange-archiving"></a>Schritt 1: Aktivieren der Exchange-Archivierung

Die Archivierung in Skype for Business Server wird hauptsächlich mithilfe der Archivierungskonfigurationseinstellungen verwaltet. Wenn Sie Skype for Business Server installieren, erhalten Sie automatisch eine einzelne globale Auflistung dieser Einstellungen. (Administratoren können optional neue Sammlungen von Archivierungseinstellungen auf Standortseite erstellen.) Standardmäßig ist die Archivierung in den globalen Einstellungen nicht aktiviert, und die Exchange-Archivierung ist in diesen Einstellungen nicht aktiviert. Um die Exchange-Archivierung verwenden zu können, müssen Administratoren sowohl die Eigenschaften EnableArchiving als auch EnableExchangeArchiving in diesen Konfigurationseinstellungen konfigurieren. Die EnableArchiving-Eigenschaft kann auf einen von drei möglichen Werten festgelegt werden:

- **Keine**. Die Archivierung ist deaktiviert. Dies ist der Standardwert. Wenn EnableArchiving auf Keine festgelegt ist, wird nichts in Ihrer Skype for Business Server-Archivierungsdatenbank oder in einer Exchange Server.

- **ImOnly**. Nur Chattaufzeichnungen werden archiviert. Wenn die Exchange-Archivierung aktiviert ist, werden diese Aufzeichnungen in einem Exchange Server. Wenn die Exchange-Archivierung deaktiviert ist, werden diese Aufzeichnungen in Skype for Business Server archiviert.

- **ImAndWebConf**. Sowohl Chat- als auch Webkonferenzaufzeichnungen werden archiviert. Wenn die Exchange-Archivierung aktiviert ist, werden diese Aufzeichnungen in der Exchange Server. Wenn die Exchange-Archivierung deaktiviert ist, werden diese Aufzeichnungen in Skype for Business Server archiviert.

Die EnableExchangeArchiving-Eigenschaft ist ein boolescher Wert: Legen Sie EnableExchangeArchiving auf True ($True) festgelegt, um die Exchange-Archivierung zu aktivieren, oder legen Sie EnableExchangeArchiving auf False ($False) zum Deaktivieren der Exchange-Archivierung. Beispielsweise ermöglicht dieser Befehl die Archivierung von Instant Messaging-Aufzeichnungen und auch die Exchange-Archivierung:

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

Um die Exchange-Archivierung zu deaktivieren, verwenden Sie einen Befehl wie den folgenden, der die Instant Messaging-Archivierung ermöglicht, aber die Archivierung in Exchange deaktiviert (mit anderen Worten, Aufzeichnungen werden in Skype for Business Server archiviert):

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> Wenn die EnableArchiving-Eigenschaft auf Keine festgelegt ist, archiviert Skype for Business Server keine Chat- und Webkonferenz-Transkripte. In diesem Fall ignoriert der Server einfach den für EnableExchangeArchiving konfigurierten Wert.

Die Exchange-Archivierung kann auch mithilfe von Skype for Business Server aktiviert (oder deaktiviert) werden. Führen Sie hierzu das folgende Verfahren aus:

1. Klicken Sie in der Systemsteuerung auf **Überwachung und Archivierung** und dann auf **Archivierungskonfiguration**.

2. Doppelklicken Sie auf der Registerkarte **Archivierungskonfiguration** auf die zu ändernde Auflistung von Archivierungseinstellungen (z. B. auf die Auflistung **Global**).

3. Klicken Sie im Bereich **Archivierungseinstellung bearbeiten** auf die Dropdownliste **Archivierungseinstellung**, und wählen Sie entweder **Chatsitzungen archivieren** (um nur Chatsitzungen zu archivieren) oder **Chat- und Webkonferenzsitzungen archivieren** (um sowohl Chat- als auch Webkonferenzsitzungen zu archivieren) aus.

4. Nachdem Sie die zu archivierenden Elemente ausgewählt haben, aktivieren Sie das Kontrollkästchen **Exchange Server** Integration, um die Exchange-Archivierung zu aktivieren. Deaktivieren Sie dieses Kontrollkästchen, um die Exchange-Archivierung zu deaktivieren.

> [!NOTE]
> Das Kontrollkästchen **Exchange Server-Integration** ist nicht verfügbar, wenn **Archivierungseinstellung** auf **Archivierung deaktivieren** festgelegt ist. Sie müssen zuerst die Archivierung aktivieren und dann die Exchange-Archivierung aktivieren.

Wenn sich Skype for Business Server und Exchange Server in derselben Gesamtstruktur befinden, wird die Archivierung für einzelne Benutzer (oder zumindest für Benutzer, die über E-Mail-Konten auf Exchange Server verfügen) mithilfe von Exchange In-Place-Halterichtlinien verwaltet. Wenn Sie Benutzer haben, die in einer früheren Version von Exchange verwaltet werden, wird die Archivierung für diese Benutzer mithilfe von Skype for Business Server-Archivierungsrichtlinien verwaltet. Beachten Sie, dass nur Benutzer mit Konten Exchange Server 2016 oder Exchange Server 2013 ihre Skype for Business-Aufzeichnungen in Exchange archivieren lassen können.

Wenn sich Skype for Business Server und Exchange Server in verschiedenen Gesamtstrukturen befinden, wird die Archivierung für einzelne Benutzer durch Konfigurieren der ExchangeArchivingPolicy-Eigenschaft für jedes einzelne Benutzerkonto verwaltet. Weitere Informationen finden Sie unter Schritt 3.

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>Schritt 2: Aktivieren der Archivierung der internen und/oder externen Kommunikation

Nachdem Sie die Archivierung (und die Exchange-Archivierung) aktiviert haben, müssen Sie die entsprechenden Archivierungsrichtlinien ändern, um sicherzustellen, dass Benutzersitzungen tatsächlich archiviert werden. Beachten Sie, dass die einfache Aktivierung der Archivierung (Schritt 1) nicht dazu führt, dass Skype for Business Server mit der Archivierung von Chatnachrichten und Webkonferenzen beginnt. Stattdessen müssen Sie mit Archivierungsrichtlinien die interne und/oder externe Archivierung aktivieren. Wenn Sie Skype for Business Server installieren, installieren Sie auch eine einzelne, globale Archivierungsrichtlinie, die zwei Eigenschaften enthält:

- **ArchiveInternal**. Wenn dieser Wert auf True ($True) festgelegt ist, werden interne Kommunikationssitzungen archiviert, an denen nur Benutzer beteiligt sind, die über Active Directory-Konten in Ihrer Organisation verfügen.

- **ArchiveExternal**. Wenn "True" ($True) festgelegt ist, werden interne Kommunikationssitzungen (Sitzungen mit mindestens einem Benutzer, der kein Active Directory-Konto in Ihrer Organisation hat) archiviert.

Standardmäßig sind beide Eigenschaftswerte auf False festgelegt, was bedeutet, dass weder interne noch externe Kommunikationssitzungen archiviert werden. Zum Ändern der globalen Richtlinie können Sie die Skype for Business Server-Verwaltungsshell und das Set-CsArchivingPolicy verwenden. Dieser Befehl ermöglicht die Archivierung interner und externer Kommunikationssitzungen:

```powershell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

Alternativ können Sie New-CsArchivingPolicy verwenden, um entweder auf Standort- oder auf Einzelbenutzerebene eine neue Richtlinie zu erstellen. Mit diesem Befehl wird z. B. eine neue Archivierungsrichtlinie auf Benutzerebene namens RedmondArchivingPolicy erstellt:

```powershell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True
```

Wenn Sie eine Richtlinie auf Einzelbenutzerebene erstellen, müssen Sie diese Richtlinie den entsprechenden Benutzern zuweisen. Beispiel:

```powershell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"
```

Archivierungsrichtlinien können auch mithilfe der Skype for Business Server-Systemsteuerung verwaltet werden. Klicken Sie in der Systemsteuerung auf **Überwachung und Archivierung,** und klicken Sie dann auf **Archivierungsrichtlinie**. Doppelklicken Sie zum Ändern einer vorhandenen Richtlinie auf die Richtlinie (z. B. Global), und  aktivieren oder  löschen Sie dann im Bereich Archivierungsrichtlinie bearbeiten die Kontrollkästchen Interne Kommunikation archivieren und externe Kommunikation archivieren nach Bedarf.  Klicken Sie zum Erstellen einer neuen Archivierungsrichtlinie auf **Neu,** und wählen Sie dann **entweder Standortrichtlinie** oder **Benutzerrichtlinie aus.** Wenn Sie eine neue Benutzerrichtlinie erstellen, müssen Sie auf  die entsprechenden Benutzerkonten (auf der Registerkarte Benutzer) zugreifen und diesen Benutzern die neue Richtlinie zuweisen.

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>Schritt 3: Konfigurieren der Eigenschaft "ExchangeArchivingPolicy"

Wenn sich Skype for Business Server und Exchange Server in verschiedenen Gesamtstrukturen befinden, reicht es nicht aus, die #A0 einfach in den Archivierungskonfigurationseinstellungen zu aktivieren. dies führt nicht dazu, dass Chat- und Webkonferenz-Transkripte in Exchange archiviert werden. Stattdessen müssen Sie auch die ExchangeArchivingPolicy-Eigenschaft für jedes der relevanten Skype for Business Server-Benutzerkonten konfigurieren. Diese Eigenschaft kann auf einen von vier möglichen Werten festgelegt werden:

1. **Nicht initialisiert**. Gibt an, dass die Archivierung auf den In-Place für das In-Place des Benutzers konfiguriert ist. Wenn In-Place für das Postfach des Benutzers nicht aktiviert wurde, werden seine Messaging- und Webkonferenz-Aufzeichnungen in Skype for Business Server archiviert.

2. **UseLyncArchivingPolicy**. Gibt an, dass die Chat- und Webkonferenz-Aufzeichnungen des Benutzers in Skype for Business Server und nicht in Exchange archiviert werden sollen.

3. **NoArchiving**. Zeigt an, dass die Chat- und Webkonferenzaufzeichnungen des Benutzers überhaupt nicht archiviert werden sollten. Beachten Sie, dass diese Einstellung alle Skype for Business Server-Archivierungsrichtlinien außer Kraft setzt, die dem Benutzer zugewiesen sind.

4. **ArchivingToExchange**. Gibt an, dass die Chat- und Webkonferenz-Aufzeichnungen des Benutzers in Exchange archiviert werden sollen, unabhängig von den In-Place-Halteeinstellungen, die dem Postfach des Benutzers zugewiesen wurden (oder nicht).

Um beispielsweise ein Benutzerkonto so zu konfigurieren, dass Chat- und Webkonferenz-Aufzeichnungen immer in Exchange archiviert werden, können Sie einen Befehl wie den folgenden in der Skype for Business Server-Verwaltungsshell verwenden:

```powershell
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

Wenn Sie dieselbe Archivierungsrichtlinie für eine Gruppe von Benutzern (z. B. alle Benutzer, die im angegebenen Registrierungsstellenpool verwaltet werden) festlegen möchten, können Sie einen ähnlichen Befehl wie den folgenden verwenden:

```powershell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

Beachten Sie, dass Sie die Skype for Business Server Management Shell (und Windows PowerShell) verwenden müssen, um den Wert der ExchangeArchivingPolicy-Eigenschaft zu konfigurieren. Diese Eigenschaft wird administratoren in Skype for Business Server nicht verfügbar gemacht.

Wenn Sie eine Liste aller Benutzer anzeigen möchten, denen eine bestimmte Archivierungsrichtlinie zugewiesen wurde, können Sie einen ähnlichen Befehl wie den folgenden verwenden. Der Befehl gibt den Active Directory-Anzeigenamen aller Benutzer zurück, für die die Eigenschaft ExchangeArchivingPolicy auf Uninitialized festgelegt ist:

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

Entsprechend gibt dieser Befehl den Anzeigenamen aller Benutzer zurück, für die die Eigenschaft ExchangeArchivingPolicy auf UseLyncArchivingPolicy festgelegt ist:

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```