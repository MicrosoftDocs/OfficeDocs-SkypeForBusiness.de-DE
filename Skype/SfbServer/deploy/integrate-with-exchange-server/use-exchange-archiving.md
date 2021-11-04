---
title: Konfigurieren Skype for Business Server für die Verwendung Exchange Server Archivierung
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
description: 'Zusammenfassung: Konfigurieren von Chattranskripts für Exchange Server 2016 oder Exchange Server 2013 und Skype for Business Server.'
ms.openlocfilehash: 44dbe1418176d7f0c33a6355480913a68baea0dd
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745291"
---
# <a name="configure-skype-for-business-server-to-use-exchange-server-archiving"></a>Konfigurieren Skype for Business Server für die Verwendung Exchange Server Archivierung

**Zusammenfassung:** Konfigurieren sie Chattranskripte für Exchange Server 2016 oder Exchange Server 2013 und Skype for Business Server.

Skype for Business Server bietet Administratoren die Möglichkeit, Chat- und Webkonferenztranskripte im Postfach Exchange Server 2016 oder Exchange Server 2013 eines Benutzers statt in einer SQL Server-Datenbank zu archivieren. Wenn Sie diese Option aktivieren, werden Transkripte in den Ordner "Löschvorgänge" im Postfach des Benutzers geschrieben. Der Ordner "Löschen" ist ein ausgeblendeter Ordner im Ordner "Wiederherstellbare Elemente". Obwohl dieser Ordner für Endbenutzer nicht sichtbar ist, wird der Ordner von der Exchange Suchmaschine indiziert und kann mit Exchange Postfachsuche und/oder Microsoft SharePoint Server 2013 ermittelt werden. Da Informationen in demselben Ordner gespeichert werden, der von der Funktion Exchange In-Place Aufbewahrung verwendet wird (die für die Archivierung von E-Mails und anderen Exchange-Kommunikationen verantwortlich ist), können Administratoren ein einzelnes Tool verwenden, um nach allen für einen Benutzer archivierten elektronischen Kommunikationen zu suchen.

> [!IMPORTANT]
> Um die Archivierung von Unterhaltungen vollständig zu deaktivieren, müssen Sie auch den Unterhaltungsverlauf deaktivieren. Weitere Informationen finden Sie in den folgenden Themen: [Verwalten der Archivierung der internen und externen Kommunikation in Skype for Business Server](/previous-versions/office/lync-server-2013/lync-server-2013-managing-the-archiving-of-internal-and-external-communications), [New-CsClientPolicy](/powershell/module/skype/new-csclientpolicy?view=skype-ps)und [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps).

Um Transkripte in Exchange Server zu archivieren, müssen Sie zunächst die Server-zu-Server-Authentifizierung zwischen Skype for Business Server und Exchange Server konfigurieren. Nachdem die Server-zu-Server-Authentifizierung eingerichtet wurde, können Sie die folgenden Aufgaben in Skype for Business Server ausführen (beachten Sie, dass Sie je nach Setup und Konfiguration möglicherweise nicht alle diese Aufgaben ausführen müssen):

1. Aktivieren Sie Exchange Archivierung, indem Sie ihre Skype for Business Server Archivierungskonfigurationseinstellungen ändern. Dieser Schritt ist für alle Bereitstellungen erforderlich.

2. Aktivieren Sie die Archivierung der internen und/oder externen Kommunikation für Ihre Benutzer. Dieser Schritt ist für alle Bereitstellungen erforderlich.

3. Konfigurieren Sie die ExchangeArchivingPolicy-Eigenschaft für jeden Benutzer. Dieser Schritt ist nur erforderlich, wenn sich Skype for Business Server und Exchange Server in unterschiedlichen Gesamtstrukturen befinden.

## <a name="step-1-enabling-exchange-archiving"></a>Schritt 1: Aktivieren Exchange Archivierung

Die Archivierung in Skype for Business Server wird in erster Linie mithilfe der Archivierungskonfigurationseinstellungen verwaltet. Wenn Sie Skype for Business Server installieren, erhalten Sie automatisch eine einzelne, globale Auflistung dieser Einstellungen. (Administratoren können optional neue Sammlungen von Archivierungseinstellungen auf Standortebene erstellen.) Standardmäßig ist die Archivierung weder in den globalen Einstellungen noch Exchange Archivierung in diesen Einstellungen aktiviert. Um Exchange Archivierung zu verwenden, müssen Administratoren die Eigenschaften EnableArchiving und EnableExchangeArchiving in diesen Konfigurationseinstellungen konfigurieren. Die EnableArchiving-Eigenschaft kann auf einen von drei möglichen Werten festgelegt werden:

- **Keine**. Die Archivierung ist deaktiviert. Dies ist der Standardwert. Wenn "EnableArchiving" auf "None" festgelegt ist, wird nichts in ihrer Skype for Business Server Archivierungsdatenbank oder in Exchange Server archiviert.

- **ImOnly**. Nur Chattaufzeichnungen werden archiviert. Wenn Exchange Archivierung aktiviert ist, werden diese Aufzeichnungen in Exchange Server archiviert. Wenn Exchange Archivierung deaktiviert ist, werden diese Aufzeichnungen in Skype for Business Server archiviert.

- **ImAndWebConf**. Sowohl Chat- als auch Webkonferenzaufzeichnungen werden archiviert. Wenn Exchange Archivierung aktiviert ist, werden diese Transkripte in Exchange Server archiviert. Wenn Exchange Archivierung deaktiviert ist, werden diese Aufzeichnungen in Skype for Business Server archiviert.

The EnableExchangeArchiving property is a Boolean value: set EnableExchangeArchiving to True ($True) to enable Exchange archiving or set EnableExchangeArchiving to False ($False) to disable Exchange archiving. Mit diesem Befehl wird beispielsweise die Archivierung von Chattranskripts und Exchange Archivierung aktiviert:

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

Um Exchange Archivierung zu deaktivieren, verwenden Sie einen Befehl ähnlich dem folgenden, der die Chatarchivierung ermöglicht, die Archivierung jedoch auf Exchange deaktiviert (mit anderen Worten, Transkripte werden in Skype for Business Server archiviert):

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> Wenn die Eigenschaft "EnableArchiving" auf "None" festgelegt ist, werden Skype for Business Server überhaupt keine Chat- und Webkonferenztranskripte archivieren. In diesem Fall ignoriert der Server einfach den für EnableExchangeArchiving konfigurierten Wert.

Exchange Archivierung kann auch mithilfe der Skype for Business Server aktiviert (oder deaktiviert) werden. Führen Sie hierzu das folgende Verfahren aus:

1. Klicken Sie in der Systemsteuerung auf **Überwachung und Archivierung** und dann auf **Archivierungskonfiguration**.

2. Doppelklicken Sie auf der Registerkarte **Archivierungskonfiguration** auf die zu ändernde Auflistung von Archivierungseinstellungen (z. B. auf die Auflistung **Global**).

3. Klicken Sie im Bereich **Archivierungseinstellung bearbeiten** auf die Dropdownliste **Archivierungseinstellung**, und wählen Sie entweder **Chatsitzungen archivieren** (um nur Chatsitzungen zu archivieren) oder **Chat- und Webkonferenzsitzungen archivieren** (um sowohl Chat- als auch Webkonferenzsitzungen zu archivieren) aus.

4. Nachdem Sie die zu archivierende Elemente ausgewählt haben, aktivieren Sie das **Kontrollkästchen Exchange Server Integration,** um Exchange Archivierung zu aktivieren. Deaktivieren Sie dieses Kontrollkästchen, um Exchange Archivierung zu deaktivieren.

> [!NOTE]
> Das Kontrollkästchen **Exchange Server-Integration** ist nicht verfügbar, wenn **Archivierungseinstellung** auf **Archivierung deaktivieren** festgelegt ist. Sie müssen zuerst die Archivierung und dann Exchange Archivierung aktivieren.

Wenn sich Skype for Business Server und Exchange Server in derselben Gesamtstruktur befinden, wird die Archivierung für einzelne Benutzer (oder zumindest für Benutzer mit E-Mail-Konten auf Exchange Server) mithilfe Exchange In-Place Aufbewahrungsrichtlinien verwaltet. Wenn Sie Benutzer haben, die in einer früheren Version von Exchange verwaltet werden, wird die Archivierung für diese Benutzer mithilfe Skype for Business Server Archivierungsrichtlinien verwaltet. Beachten Sie, dass nur Benutzer mit Konten Exchange Server 2016 oder Exchange Server 2013 ihre Skype for Business Transkripte in Exchange archivieren können.

Wenn sich Skype for Business Server und Exchange Server in unterschiedlichen Gesamtstrukturen befinden, wird die Archivierung für einzelne Benutzer durch Konfigurieren der ExchangeArchivingPolicy-Eigenschaft für jedes einzelne Benutzerkonto verwaltet. Weitere Informationen finden Sie in Schritt 3.

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>Schritt 2: Aktivieren der Archivierung der internen und/oder externen Kommunikation

Nachdem Sie die Archivierung (und Exchange Archivierung) aktiviert haben, müssen Sie die entsprechenden Archivierungsrichtlinien ändern, um sicherzustellen, dass Benutzersitzungen tatsächlich archiviert werden. Beachten Sie, dass das einfache Aktivieren der Archivierung (Schritt 1) nicht dazu führt, dass Skype for Business Server mit der Archivierung von Chat- und Webkonferenztranskripten beginnen. Stattdessen müssen Sie mit Archivierungsrichtlinien die interne und/oder externe Archivierung aktivieren. Wenn Sie Skype for Business Server installieren, installieren Sie auch eine einzelne globale Archivierungsrichtlinie, die zwei Eigenschaften enthält:

- **ArchiveInternal**. Bei Festlegung auf "True" ($True) wird angegeben, dass interne Kommunikationssitzungen, an denen nur Benutzer beteiligt sind, die über Active Directory-Konten in Ihrer Organisation verfügen, archiviert werden.

- **ArchiveExternal**. Bei Festlegung auf "True" ($True) wird angegeben, dass interne Kommunikationssitzungen (Sitzungen, an denen mindestens ein Benutzer beteiligt ist, der kein Active Directory-Konto in Ihrer Organisation besitzt) archiviert werden.

Standardmäßig werden beide Eigenschaftswerte auf "False" festgelegt, was bedeutet, dass weder interne noch externe Kommunikationssitzungen archiviert werden. Zum Ändern der globalen Richtlinie können Sie die Skype for Business Server Verwaltungsshell und das Cmdlet Set-CsArchivingPolicy verwenden. Dieser Befehl ermöglicht die Archivierung von internen und externen Kommunikationssitzungen:

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

Archivierungsrichtlinien können auch mithilfe der Skype for Business Server Systemsteuerung verwaltet werden. Klicken Sie in der Systemsteuerung auf **"Überwachung und Archivierung",** und klicken Sie dann auf **"Archivierungsrichtlinie".** Doppelklicken Sie zum Ändern einer vorhandenen Richtlinie auf die Richtlinie (z. B. global), und aktivieren oder deaktivieren Sie dann im Bereich **"Archivierungsrichtlinie bearbeiten"** die Kontrollkästchen **"Interne Kommunikation archivieren"** und **"Externe Kommunikation archivieren"** nach Bedarf. Klicken Sie zum Erstellen einer neuen Archivierungsrichtlinie auf **"Neu",** und wählen Sie dann entweder **"Standortrichtlinie"** oder **"Benutzerrichtlinie"** aus. Wenn Sie eine neue Benutzerrichtlinie erstellen, müssen Sie auf die entsprechenden Benutzerkonten (über die Registerkarte **"Benutzer")** zugreifen und diesen Benutzern die neue Richtlinie zuweisen.

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>Schritt 3: Konfigurieren der Eigenschaft "ExchangeArchivingPolicy"

Wenn sich Skype for Business Server und Exchange Server in unterschiedlichen Gesamtstrukturen befinden, reicht es nicht aus, einfach Exchange Archivierung in den Archivierungskonfigurationseinstellungen zu aktivieren. dies führt nicht dazu, dass Chat- und Webkonferenztranskripte in Exchange archiviert werden. Stattdessen müssen Sie auch die ExchangeArchivingPolicy-Eigenschaft für jedes der relevanten Skype for Business Server Benutzerkonten konfigurieren. Diese Eigenschaft kann auf einen von vier möglichen Werten festgelegt werden:

1. **Nicht initialisiert.** Gibt an, dass die Archivierung auf den Einstellungen für das In-Place Haltebereich basiert, die für das postfach Exchange des Benutzers konfiguriert sind. Wenn In-Place Aufbewahrung für das Postfach des Benutzers nicht aktiviert wurde, werden die Aufzeichnungen seiner Messaging- und Webkonferenzen in Skype for Business Server archiviert.

2. **UseLyncArchivingPolicy**. Gibt an, dass die Chat- und Webkonferenztranskripte des Benutzers in Skype for Business Server und nicht in Exchange archiviert werden sollen.

3. **NoArchiving**. Zeigt an, dass die Chat- und Webkonferenzaufzeichnungen des Benutzers überhaupt nicht archiviert werden sollten. Beachten Sie, dass diese Einstellung alle Skype for Business Server Archivierungsrichtlinien überschreibt, die dem Benutzer zugewiesen sind.

4. **ArchivingToExchange**. Gibt an, dass die Chat- und Webkonferenztranskripte des Benutzers in Exchange archiviert werden sollen, unabhängig von den Einstellungen für das In-Place Haltebereichs, die dem Postfach des Benutzers zugewiesen wurden (oder nicht).

Um beispielsweise ein Benutzerkonto so zu konfigurieren, dass Chat- und Webkonferenztranskripte immer in Exchange archiviert werden, können Sie einen Befehl wie den folgenden aus der Skype for Business Server Verwaltungsshell verwenden:

```powershell
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

Wenn Sie dieselbe Archivierungsrichtlinie für eine Gruppe von Benutzern (z. B. alle Benutzer, die im angegebenen Registrierungsstellenpool verwaltet werden) festlegen möchten, können Sie einen ähnlichen Befehl wie den folgenden verwenden:

```powershell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

Beachten Sie, dass Sie die Skype for Business Server-Verwaltungsshell (und Windows PowerShell) verwenden müssen, um den Wert der ExchangeArchivingPolicy-Eigenschaft zu konfigurieren. Diese Eigenschaft wird für Administratoren im Skype for Business Server nicht verfügbar gemacht.

Wenn Sie eine Liste aller Benutzer anzeigen möchten, denen eine bestimmte Archivierungsrichtlinie zugewiesen wurde, können Sie einen ähnlichen Befehl wie den folgenden verwenden. Der Befehl gibt den Active Directory-Anzeigenamen aller Benutzer zurück, für die die Eigenschaft ExchangeArchivingPolicy auf Uninitialized festgelegt ist:

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

Entsprechend gibt dieser Befehl den Anzeigenamen aller Benutzer zurück, für die die Eigenschaft ExchangeArchivingPolicy auf UseLyncArchivingPolicy festgelegt ist:

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```