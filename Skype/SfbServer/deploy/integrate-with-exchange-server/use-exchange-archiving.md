---
title: Konfigurieren von Skype für Business Server mit Exchange Server-Archivierung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
description: 'Zusammenfassung: Konfigurieren von Instant Messaging-Protokolle für Exchange Server 2016 oder Exchange Server 2013 und Skype für Business Server.'
ms.openlocfilehash: a810f2e3eb3546eae5b3e04b2b1a9e83b7f9dbab
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894232"
---
# <a name="configure-skype-for-business-server-to-use-exchange-server-archiving"></a>Konfigurieren von Skype für Business Server mit Exchange Server-Archivierung

**Zusammenfassung:** Konfigurieren von Instant Messaging-Protokolle für Exchange Server 2016 oder Exchange Server 2013 und Skype für Business Server.

Skype für Business Server bietet Administratoren die Möglichkeit, instant messaging und webkonferenzaufzeichnungen zu einer SQL Server-Datenbank, statt 2016 der Exchange-Server oder Exchange Server 2013-Postfach eines Benutzers archiviert. Wenn Sie diese Option aktivieren, werden Aufzeichnungen in den Löschordner des Benutzerpostfachs geschrieben. Der Löschordner ist ein ausgeblendeter Ordner im Ordner „Wiederherstellbare Elemente“. Obwohl diese Ordner nicht für Endbenutzer angezeigt wird, wird der Ordner wird vom Suchmodul Exchange indiziert und mithilfe der Exchange-Postfach-Suche und/oder Microsoft SharePoint Server 2013 ermittelt werden kann. Da im gleichen Ordner wie von der Exchange Compliance-Archiv-Funktion (verantwortlich für die Archivierung von e-Mail und anderen Exchange) gespeichert werden, können Administratoren ein einziges Tool für die Suche nach die elektronischen Kommunikation für archiviert eine Benutzer.

> [!IMPORTANT]
> Um die Archivierung von Unterhaltungen vollständig zu deaktivieren, müssen Sie außerdem den Unterhaltungsverlauf aktivieren. Weitere Informationen finden Sie unter den folgenden Themen: [Verwalten der Archivierung der internen und externen Kommunikation in Skype für Business Server](https://technet.microsoft.com/library/6c2cf941-3204-4f1a-a7e0-416c828056d9.aspx), [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps)und [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).

Zum Archivieren von Aufzeichnungen auf Exchange-Server müssen Sie durch Konfigurieren der Server-zu-Server-Authentifizierung zwischen Skype für Business Server und Exchange Server beginnen. Nach Server-zu-Server-Authentifizierung eingerichtet ist, können Sie dann führen Sie die folgenden Aufgaben in Skype für Business Server (Beachten Sie, dass je nach der Installation und Konfiguration nicht möglicherweise alle diese Aufgaben ausführen müssen):

1. Aktivieren Sie die Exchange-Archivierung durch Ihre Skype für archivierungskonfigurationseinstellungen Business Server ändern. Dieser Schritt ist für alle Bereitstellungen erforderlich.

2. Aktivieren Sie die Archivierung der internen und/oder externen Kommunikation für Ihre Benutzer. Dieser Schritt ist für alle Bereitstellungen erforderlich.

3. Konfigurieren Sie die Eigenschaft „ExchangeArchivingPolicy“ für jeden Benutzer. Dieser Schritt ist nur erforderlich, wenn Skype für Business Server und Exchange-Server befinden sich in unterschiedlichen Gesamtstrukturen.

## <a name="step-1-enabling-exchange-archiving"></a>Schritt 1: Aktivieren der Exchange-Archivierung

Archivierung in Skype für Business Server wird in erster Linie mithilfe von archivierungskonfigurationseinstellungen verwaltet. Bei der Installation von Skype für Business Server erhalten Sie eine einzelne globale Auflistung von diese Einstellungen automatisch. (Administratoren können optional neue Sammlungen von archivierungseinstellungen auf Standortebene erstellen.) In der Standardeinstellung Archivierung in den globalen Einstellungen nicht aktiviert ist, noch in diese Einstellungen aktiviert Exchange-Archivierung ist. Um die Exchange-Archivierung verwenden, müssen Administratoren die EnableArchiving und die EnableExchangeArchiving-Eigenschaften in dieser Konfigurationseinstellungen konfigurieren. Die Eigenschaft „EnableArchiving“ kann auf einen von drei möglichen Werten festgelegt werden:

- **None**. Archivierung ist deaktiviert. Dies ist der Standardwert. Wenn EnableArchiving auf None festgelegt ist, und klicken Sie dann nothing werden Ihre Skype archiviert werden in einem für Business Server Archivierungsdatenbank oder in Exchange Server.

- **ImOnly**. Nur Sofortnachricht Protokolle archiviert werden. Exchange-Archivierung aktiviert ist, werden diese Protokolle in Exchange Server archiviert. Wenn Exchange-Archivierung deaktiviert ist werden dann diese Protokolle zu Skype für Business Server archiviert.

- **ImAndWebConf**. Instant Messaging-Protokolle und webkonferenzaufzeichnungen archiviert werden. Bei aktiviertem Exchange-Archivierung in Exchange Server werden diese Protokolle archiviert werden. Wenn Exchange-Archivierung deaktiviert ist werden dann diese Protokolle zu Skype für Business Server archiviert.

Die EnableExchangeArchiving-Eigenschaft ist ein Wert vom Typ Boolean: Legen Sie EnableExchangeArchiving auf "true" ($True) zum Aktivieren der Exchange-Archivierung oder festlegen EnableExchangeArchiving auf "false" ($False) Exchange-Archivierung deaktivieren. Mit diesem Befehl wird beispielsweise ermöglicht die Archivierung von instant messaging-Protokolle und lässt zu, Exchange-Archivierung:

```
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

Verwenden Sie zum Deaktivieren des Exchange-Archivierung einen Befehl ähnlich dem folgenden, die instant messaging-Archivierung ermöglicht jedoch Archivierung in Exchange (mit anderen Worten, Aufzeichnungen werden auf archiviert Skype für Business Server):

```
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> Wenn die EnableArchiving-Eigenschaft auf None festgelegt ist, werden dann Skype für Business Server nicht instant messaging und webkonferenzaufzeichnungen überhaupt archiviert. In diesem Fall ignoriert der Server einfach den für EnableExchangeArchiving konfigurierten Wert.

Exchange-Archivierung kann auch aktiviert (oder deaktiviert werden) mit der Skype für Business Server. Führen Sie hierzu das folgende Verfahren aus:

1. Klicken Sie in der Systemsteuerung auf **Überwachung und Archivierung** und dann auf **Archivierungskonfiguration**.

2. Doppelklicken Sie auf der Registerkarte **Archivierungskonfiguration** auf die zu ändernde Auflistung von Archivierungseinstellungen (z. B. auf die Auflistung **Global**).

3. Klicken Sie im Bereich **Archivierungseinstellung bearbeiten** auf die Dropdownliste **Archivierungseinstellung** und wählen Sie entweder **Chatsitzungen archivieren** (um nur Chatsitzungen zu archivieren) oder **Chat- und Webkonferenzsitzungen archivieren** (um sowohl Chat- als auch Webkonferenzsitzungen zu archivieren).

4. Nach dem Auswählen der zu archivierende Elemente an, das Kontrollkästchen Sie **Integration von Exchange Server** zu Exchange-Archivierung zu aktivieren. Deaktivieren Sie dieses Kontrollkästchen, um Exchange-Archivierung zu deaktivieren.

> [!NOTE]
> Das Kontrollkästchen **Exchange Server-Integration** ist nicht verfügbar, wenn **Archivierungseinstellung** auf **Archivierung deaktivieren** festgelegt ist. Sie müssen Archivierung erste aktivieren und Exchange-Archivierung zu aktivieren.

Wenn Skype für Business Server und Exchange-Server sich in derselben Gesamtstruktur befinden, klicken Sie dann die Archivierung für einzelne Benutzer (oder mindestens für Benutzer mit e-Mail-auf Exchange-Server Konten) wird mithilfe von Exchange In-Place Hold Richtlinien verwaltet. Wenn Sie haben werden Benutzer, die in einer früheren Version von Exchange-Archivierung für diese Benutzer verwaltet werden mithilfe von Skype für Archivierungsrichtlinien Business Server verwaltet. Beachten Sie, dass nur Benutzer mit Konten in Exchange Server 2016 oder Exchange Server 2013 ihre Skype für Business Protokolle in Exchange archiviert werden können.

Skype für Business Server und Exchange Server in unterschiedlichen Gesamtstrukturen befinden, und klicken Sie dann die Archivierung für einzelne Benutzer verwaltet wird, indem Sie die Eigenschaft ExchangeArchivingPolicy für jedes einzelne Benutzerkonto konfigurieren. Weitere Informationen finden Sie in Schritt 3.

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>Schritt 2: Aktivieren der Archivierung der internen und/oder externen Kommunikation

Nachdem Sie die Archivierung aktiviert haben (und Exchange-Archivierung) müssen Sie dann die entsprechenden Archivierungsrichtlinien um sicherzustellen, dass benutzersitzungen tatsächlich archiviert werden ändern. Beachten Sie, dass einfach Aktivieren der Archivierung (Schritt 1) keine Skype für Business Server mit dem Archivieren Sofortnachrichten beginnen und webkonferenzaufzeichnungen verursacht. Stattdessen müssen Sie mit Archivierungsrichtlinien die interne und/oder externe Archivierung aktivieren. Bei der Installation von Skype für Business Server installieren Sie auch eine globales Archivierungsrichtlinie, die zwei Eigenschaften enthält:

- **ArchiveInternal**: Ist diese Eigenschaft auf „True“ ($True) gesetzt, werden interne Kommunikationssitzungen archiviert, an denen nur Benutzer in der Organisation beteiligt sind, die ein Active Directory-Konto besitzen.

- **ArchiveExternal**: Ist diese Eigenschaft auf „True“ ($True) gesetzt, werden externe Kommunikationssitzungen archiviert (Sitzungen, an denen mindestens ein Benutzer beteiligt ist, der kein Active Directory-Konto in Ihrer Organisation besitzt).

Standardmäßig werden beide Eigenschaftswerte auf "false" können Bedeutung festgelegt, dass weder interne noch externe kommunikationssitzungen archiviert werden. Um die globale Richtlinie zu ändern, können Sie die Skype für Business Server-Verwaltungsshell und das Set-CsArchivingPolicy-Cmdlet verwenden. Dieser Befehl ermöglicht die Archivierung sowohl interne und externe kommunikationssitzungen:

```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

Alternativ können Sie „New-CsArchivingPolicy“ verwenden, um entweder auf Standort- oder auf Einzelbenutzerebene eine neue Richtlinie zu erstellen. Mit diesem Befehl wird z. B. eine neue Archivierungsrichtlinie auf Benutzerebene namens „RedmondArchivingPolicy“ erstellt:

```
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True
```

Wenn Sie eine Richtlinie auf Einzelbenutzerebene erstellen, müssen Sie diese Richtlinie den entsprechenden Benutzern zuweisen. Beispiel:

```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"
```

Archivierungsrichtlinien kann auch mithilfe der Skype für Business Server-Systemsteuerung verwaltet werden. Klicken Sie in der Systemsteuerung auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**. Um eine vorhandene Richtlinie zu ändern, doppelklicken Sie auf die Richtlinie (z. B. Global) und klicken Sie dann im Bereich **Bearbeiten der Archivierungsrichtlinie** aktivieren oder deaktivieren Sie die **interne Kommunikation archivieren** , und das Kontrollkästchen **externe Kommunikation archivieren** nach Bedarf. Zum Erstellen einer neuen Archivierungsrichtlinie auf **neu** , und wählen Sie dann auf **Standort-** oder **Benutzerrichtlinie**. Wenn Sie eine neue Benutzerrichtlinie erstellen, müssen Sie (über die Registerkarte „Benutzer“) auf die entsprechenden Benutzerkonten zugreifen und diesen Benutzern die neue Richtlinie zuweisen.

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>Schritt 3: Konfigurieren der Eigenschaft "ExchangeArchivingPolicy"

Skype für Business Server und Exchange Server in unterschiedlichen Gesamtstrukturen befinden, ist es nicht genug sind, um die Archivierung in archivierungskonfigurationseinstellungen Exchange einfach zu aktivieren; die nicht instant messaging und webkonferenzaufzeichnungen in Exchange archiviert führt. Stattdessen müssen Sie die Eigenschaft ExchangeArchivingPolicy auf jedem der relevanten Skype für Benutzerkonten Business Server konfigurieren. Diese Eigenschaft kann auf einen der vier mögliche Werte festgelegt werden:

1. **Nicht initialisiert**. Gibt an, dass die Archivierung die Compliance-Archivs Einstellungen für die Exchange-Postfach des Benutzers konfiguriert sind basieren soll. Wenn Sie Compliance-Archiv nicht auf das Postfach des Benutzers aktiviert wurde und der Benutzer seine messaging haben und Web Conferencing Protokolle archiviert in Skype für Business Server.

2. **Uselyncarchivingpolicy festgelegt**. Gibt an, dass des Benutzers instant messaging und webkonferenzaufzeichnungen in Skype für Business Server nicht in Exchange archiviert werden sollen.

3. **NoArchiving**. Gibt an, dass des Benutzers instant messaging und webkonferenzaufzeichnungen nicht in allen archiviert werden sollen. Beachten Sie, dass diese Einstellung für Business Server, die dem Benutzer zugewiesene Archivierungsrichtlinien Skype außer Kraft gesetzt.

4. **ArchivingToExchange**: zeigt an, dass die Chat- und Webkonferenzaufzeichnungen des Benutzers unabhängig von den Compliance-Archiv-Einstellungen, die ggf. Gibt an, die des Benutzers instant messaging und Webkonferenzen Protokolle zu Exchange müssen, unabhängig von den Einstellungen In-Place Hold archiviert werden, die haben (oder nicht) auf das Postfach des Benutzers zugewiesen wurden.

Um ein Benutzerkonto so konfigurieren, dass instant messaging und webkonferenzaufzeichnungen immer auf Exchange archiviert werden können Sie beispielsweise einen Befehl wie den folgenden von der Skype für Business Server-Verwaltungsshell verwenden:

```
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

Wenn Sie dieselbe Archivierungsrichtlinie für eine Gruppe von Benutzern (z. B. alle Benutzer, die im angegebenen Registrierungsstellenpool verwaltet werden) festlegen möchten, können Sie einen ähnlichen Befehl wie den folgenden verwenden:

```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

Beachten Sie, dass die Skype für Business Server-Verwaltungsshell (und Windows PowerShell) zum Konfigurieren der Wert der Eigenschaft "exchangearchivingpolicy" verwendet werden muss. Diese Eigenschaft wird nicht für Administratoren in der Skype für Business Server angezeigt.

Wenn Sie eine Liste aller Benutzer anzeigen möchten, denen eine bestimmte Archivierungsrichtlinie zugewiesen wurde, können Sie einen ähnlichen Befehl wie den folgenden verwenden. Der Befehl gibt den Active Directory-Anzeigenamen aller Benutzer zurück, für die die Eigenschaft „ExchangeArchivingPolicy“ auf „Uninitialized“ festgelegt ist:

```
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

Entsprechend gibt dieser Befehl den Anzeigenamen aller Benutzer zurück, für die die Eigenschaft „ExchangeArchivingPolicy“ auf „UseLyncArchivingPolicy“ festgelegt ist:

```
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```


