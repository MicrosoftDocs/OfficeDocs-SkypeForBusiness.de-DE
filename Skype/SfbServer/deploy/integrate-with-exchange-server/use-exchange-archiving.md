---
title: Konfigurieren von Skype for Business Server für die Verwendung der Exchange Server-Archivierung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
description: 'Zusammenfassung: Konfigurieren von im-Transkripten für Exchange Server 2016 oder Exchange Server 2013 und Skype for Business Server.'
ms.openlocfilehash: b24353a9742a48b35e21ac00df40a04fa60e444b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278070"
---
# <a name="configure-skype-for-business-server-to-use-exchange-server-archiving"></a>Konfigurieren von Skype for Business Server für die Verwendung der Exchange Server-Archivierung

**Zusammenfassung:** Konfigurieren von Chat Abschriften für Exchange Server 2016 oder Exchange Server 2013 und Skype for Business Server.

Skype for Business Server bietet Administratoren die Möglichkeit, Sofortnachrichten und Webkonferenz Protokolle im Exchange Server 2016-oder Exchange Server 2013-Postfach eines Benutzers zu archivieren, anstatt eine SQL Server-Datenbank zu verwenden. Wenn Sie diese Option aktivieren, werden Aufzeichnungen in den Löschordner des Benutzerpostfachs geschrieben. Der Löschordner ist ein ausgeblendeter Ordner im Ordner „Wiederherstellbare Elemente“. Obwohl dieser Ordner für Endbenutzer nicht sichtbar ist, wird der Ordner von der Exchange-Suchmaschine indiziert und kann mithilfe der Exchange-Postfachsuche und/oder Microsoft SharePoint Server 2013 ermittelt werden. Da die Informationen im gleichen Ordner gespeichert sind, der von der Exchange-Funktion für in-situ-Speicher (für das Archivieren von e-Mails und anderer Exchange-Kommunikation) verwendet wird, können Administratoren ein einzelnes Tool verwenden, um nach der gesamten elektronischen Kommunikation zu suchen, die für eine archiviert wurde. Benutzer.

> [!IMPORTANT]
> Um die Archivierung von Unterhaltungen vollständig zu deaktivieren, müssen Sie außerdem den Unterhaltungsverlauf aktivieren. Weitere Informationen finden Sie unter den folgenden Themen: [Verwalten der Archivierung von internen und externen Kommunikationen in Skype for Business Server](https://technet.microsoft.com/library/6c2cf941-3204-4f1a-a7e0-416c828056d9.aspx), [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps)und [CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).

Um Transkripte auf Exchange Server zu archivieren, müssen Sie zunächst die Server-zu-Server-Authentifizierung zwischen Skype for Business Server und Exchange Server konfigurieren. Nachdem die Server-zu-Server-Authentifizierung eingerichtet ist, können Sie die folgenden Aufgaben in Skype for Business Server ausführen (Beachten Sie, dass Sie – je nach Konfiguration und Konfiguration – möglicherweise nicht alle diese Aufgaben ausführen müssen):

1. Aktivieren Sie die Exchange-Archivierung, indem Sie Ihre Konfigurationseinstellungen für die Archivierungskonfiguration von Skype for Business Server ändern. Dieser Schritt ist für alle Bereitstellungen erforderlich.

2. Aktivieren Sie die Archivierung der internen und/oder externen Kommunikation für Ihre Benutzer. Dieser Schritt ist für alle Bereitstellungen erforderlich.

3. Konfigurieren Sie die Eigenschaft „ExchangeArchivingPolicy“ für jeden Benutzer. Dieser Schritt ist nur erforderlich, wenn sich Skype for Business Server und Exchange Server in unterschiedlichen Gesamtstrukturen befinden.

## <a name="step-1-enabling-exchange-archiving"></a>Schritt 1: Aktivieren der Exchange-Archivierung

Die Archivierung in Skype for Business Server wird hauptsächlich mithilfe der Archivierungs Konfigurationseinstellungen verwaltet. Wenn Sie Skype for Business Server installieren, erhalten Sie automatisch eine einzige globale Sammlung dieser Einstellungen. (Administratoren können optional neue Sammlungen von Archivierungseinstellungen im Website Bereich erstellen.) Standardmäßig ist die Archivierung in den globalen Einstellungen nicht aktiviert, und die Exchange-Archivierung ist in diesen Einstellungen nicht aktiviert. Um die Exchange-Archivierung verwenden zu können, müssen Administratoren sowohl die EnableArchiving-als auch die EnableExchangeArchiving-Eigenschaft in diesen Konfigurationseinstellungen konfigurieren. Die Eigenschaft „EnableArchiving“ kann auf einen von drei möglichen Werten festgelegt werden:

- **Keine**. Die Archivierung ist deaktiviert. Dies ist der Standardwert. Wenn EnableArchiving auf "keine" gesetzt ist, wird in Ihrer Skype for Business Server-Archivierungsdatenbank oder in Exchange Server nichts archiviert.

- **** Ist nicht verfügbar. Es werden nur Sofortnachrichten Abschriften archiviert. Wenn die Exchange-Archivierung aktiviert ist, werden diese Protokolle in Exchange Server archiviert. Wenn die Exchange-Archivierung deaktiviert ist, werden diese Protokolle in Skype for Business Server archiviert.

- **ImAndWebConf**. Sowohl Sofortnachrichten Protokolle als auch Webkonferenz-Transkripte werden archiviert. Wenn die Exchange-Archivierung aktiviert ist, werden diese Protokolle in Exchange Server archiviert. Wenn die Exchange-Archivierung deaktiviert ist, werden diese Protokolle in Skype for Business Server archiviert.

Die EnableExchangeArchiving-Eigenschaft ist ein boolescher Wert: setzen Sie EnableExchangeArchiving auf true ($true), um die Exchange-Archivierung zu aktivieren oder EnableExchangeArchiving auf false festzulegen ($false), um die Exchange-Archivierung zu deaktivieren. Mit diesem Befehl können Sie beispielsweise die Archivierung von Sofortnachrichten Abschriften und die Exchange-Archivierung aktivieren:

```
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

Wenn Sie die Exchange-Archivierung deaktivieren möchten, verwenden Sie einen Befehl ähnlich der folgenden, der die Sofortnachrichten Archivierung ermöglicht, aber die Archivierung in Exchange deaktiviert (d. h., Transkripte werden in Skype for Business Server archiviert):

```
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> Wenn die EnableArchiving-Eigenschaft auf None eingestellt ist, werden von Skype for Business Server keine Sofortnachrichten und Webkonferenz-Transkripte archiviert. In diesem Fall ignoriert der Server einfach den für EnableExchangeArchiving konfigurierten Wert.

Die Exchange-Archivierung kann auch über den Skype for Business-Server aktiviert (oder deaktiviert) werden. Führen Sie hierzu das folgende Verfahren aus:

1. Klicken Sie in der Systemsteuerung auf **Überwachung und Archivierung** und dann auf **Archivierungskonfiguration**.

2. Doppelklicken Sie auf der Registerkarte **Archivierungskonfiguration** auf die zu ändernde Auflistung von Archivierungseinstellungen (z. B. auf die Auflistung **Global**).

3. Klicken Sie im Bereich **Archivierungseinstellung bearbeiten** auf die Dropdownliste **Archivierungseinstellung** und wählen Sie entweder **Chatsitzungen archivieren** (um nur Chatsitzungen zu archivieren) oder **Chat- und Webkonferenzsitzungen archivieren** (um sowohl Chat- als auch Webkonferenzsitzungen zu archivieren).

4. Nachdem Sie die zu archivierende Elemente ausgewählt haben, aktivieren Sie das Kontrollkästchen **Exchange-Server Integration** , um die Exchange-Archivierung zu aktivieren. Deaktivieren Sie dieses Kontrollkästchen, um die Exchange-Archivierung zu deaktivieren.

> [!NOTE]
> Das Kontrollkästchen **Exchange Server-Integration** ist nicht verfügbar, wenn **Archivierungseinstellung** auf **Archivierung deaktivieren** festgelegt ist. Sie müssen zuerst die Archivierung aktivieren und dann die Exchange-Archivierung aktivieren.

Wenn sich Skype for Business Server und Exchange Server in derselben Gesamtstruktur befinden, wird die Archivierung für einzelne Benutzer (oder zumindest für Benutzer mit e-Mail-Konten auf Exchange Server) mithilfe von Exchange in-situ-Speicherrichtlinien verwaltet. Wenn Sie über Benutzer verfügen, die in einer früheren Version von Exchange verwaltet werden, wird die Archivierung für diese Benutzer mithilfe von Skype for Business Server-Archivierungsrichtlinien verwaltet. Beachten Sie, dass nur Benutzer mit Konten auf Exchange Server 2016 oder Exchange Server 2013 Ihre Skype for Business-Transkripte in Exchange archivieren können.

Wenn sich Skype for Business Server und Exchange Server in unterschiedlichen Gesamtstrukturen befinden, wird die Archivierung für einzelne Benutzer durch Konfigurieren der ExchangeArchivingPolicy-Eigenschaft für jedes einzelne Benutzerkonto verwaltet. Weitere Informationen finden Sie in Schritt 3.

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>Schritt 2: Aktivieren der Archivierung der internen und/oder externen Kommunikation

Nachdem Sie die Archivierung (und die Exchange-Archivierung) aktiviert haben, müssen Sie die entsprechenden Archivierungsrichtlinien ändern, um sicherzustellen, dass Benutzersitzungen tatsächlich archiviert werden. Beachten Sie, dass die Archivierung von Instant Messaging-und Webkonferenz-Transkripten nicht durch die Aktivierung von Skype for Business Server gestartet werden kann (Schritt 1). Stattdessen müssen Sie mit Archivierungsrichtlinien die interne und/oder externe Archivierung aktivieren. Wenn Sie Skype for Business Server installieren, installieren Sie auch eine einzige globale Archivierungsrichtlinie, die zwei Eigenschaften enthält:

- **ArchiveInternal**: Ist diese Eigenschaft auf „True“ ($True) gesetzt, werden interne Kommunikationssitzungen archiviert, an denen nur Benutzer in der Organisation beteiligt sind, die ein Active Directory-Konto besitzen.

- **ArchiveExternal**: Ist diese Eigenschaft auf „True“ ($True) gesetzt, werden externe Kommunikationssitzungen archiviert (Sitzungen, an denen mindestens ein Benutzer beteiligt ist, der kein Active Directory-Konto in Ihrer Organisation besitzt).

Standardmäßig sind beide Eigenschaftenwerte auf "false" festgelegt, was bedeutet, dass weder interne noch externe Kommunikationssitzungen archiviert werden. Zum Ändern der globalen Richtlinie können Sie die Skype for Business Server-Verwaltungsshell und das Cmdlet "Satz-CsArchivingPolicy" verwenden. Dieser Befehl ermöglicht die Archivierung interner und externer Kommunikationssitzungen:

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

Archivierungsrichtlinien können auch über das Skype Control Panel für Unternehmen Server verwaltet werden. Klicken Sie in der Systemsteuerung auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**. Wenn Sie eine vorhandene Richtlinie ändern möchten, doppelklicken Sie auf die Richtlinie (z. b. Global), und aktivieren oder deaktivieren Sie dann im Bereich **Archivierungsrichtlinie bearbeiten** die Kontrollkästchen **interne Kommunikation** und **externe Kommunikation archivieren** nach Bedarf. Wenn Sie eine neue Archivierungsrichtlinie erstellen möchten, klicken Sie auf **neu** , und wählen Sie dann entweder **Website Richtlinie** oder **Benutzerrichtlinie**aus. Wenn Sie eine neue Benutzerrichtlinie erstellen, müssen Sie (über die Registerkarte „Benutzer“) auf die entsprechenden Benutzerkonten zugreifen und diesen Benutzern die neue Richtlinie zuweisen.

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>Schritt 3: Konfigurieren der Eigenschaft "ExchangeArchivingPolicy"

Wenn sich Skype for Business Server und Exchange Server in unterschiedlichen Gesamtstrukturen befinden, reicht es nicht aus, die Exchange-Archivierung einfach in den Archivierungs Konfigurationseinstellungen zu aktivieren. Dadurch werden keine Instant Messaging-und Webkonferenz Protokolle in Exchange archiviert. Stattdessen müssen Sie auch die ExchangeArchivingPolicy-Eigenschaft für jedes der relevanten Skype for Business Server-Benutzerkonten konfigurieren. Diese Eigenschaft kann auf einen von vier möglichen Werten eingestellt werden:

1. Nicht **Initialisiert**. Gibt an, dass die Archivierung auf den in-situ-Speicherungs Einstellungen basiert, die für das Exchange-Postfach des Benutzers konfiguriert sind. Wenn in-situ-Speicher für das Postfach des Benutzers nicht aktiviert wurde, wird der Benutzer in Skype for Business Server seine Messaging-und Webkonferenz-Transkripte archiviert.

2. **UseLyncArchivingPolicy**. Gibt an, dass die Protokolle für Sofortnachrichten und Webkonferenzen des Benutzers in Skype for Business Server und nicht in Exchange archiviert werden sollen.

3. **** Noarchiving. Gibt an, dass die Protokolle für Chatnachrichten und Webkonferenzen des Benutzers überhaupt nicht archiviert werden sollen. Beachten Sie, dass diese Einstellung alle Skype for Business Server-Archivierungsrichtlinien außer Kraft setzt, die dem Benutzer zugewiesen sind.

4. **ArchivingToExchange**: zeigt an, dass die Chat- und Webkonferenzaufzeichnungen des Benutzers unabhängig von den Compliance-Archiv-Einstellungen, die ggf. Gibt an, dass die Protokolle des Benutzers für Sofortnachrichten und Webkonferenzen in Exchange unabhängig von den in-situ-Speicher-Einstellungen, die dem Postfach des Benutzers zugewiesen wurden (oder nicht), archiviert werden sollen.

Wenn Sie beispielsweise ein Benutzerkonto so konfigurieren möchten, dass Sofortnachrichten und Webkonferenz Protokolle immer in Exchange archiviert werden, können Sie einen ähnlichen Befehl wie den folgenden in der Skype for Business Server-Verwaltungsshell verwenden:

```
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

Wenn Sie dieselbe Archivierungsrichtlinie für eine Gruppe von Benutzern (z. B. alle Benutzer, die im angegebenen Registrierungsstellenpool verwaltet werden) festlegen möchten, können Sie einen ähnlichen Befehl wie den folgenden verwenden:

```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

Beachten Sie, dass Sie die Skype for Business Server-Verwaltungsshell (und Windows PowerShell) verwenden müssen, um den Wert der ExchangeArchivingPolicy-Eigenschaft zu konfigurieren. Diese Eigenschaft wird für Administratoren im Skype for Business-Server nicht verfügbar gemacht.

Wenn Sie eine Liste aller Benutzer anzeigen möchten, denen eine bestimmte Archivierungsrichtlinie zugewiesen wurde, können Sie einen ähnlichen Befehl wie den folgenden verwenden. Der Befehl gibt den Active Directory-Anzeigenamen aller Benutzer zurück, für die die Eigenschaft „ExchangeArchivingPolicy“ auf „Uninitialized“ festgelegt ist:

```
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

Entsprechend gibt dieser Befehl den Anzeigenamen aller Benutzer zurück, für die die Eigenschaft „ExchangeArchivingPolicy“ auf „UseLyncArchivingPolicy“ festgelegt ist:

```
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```


