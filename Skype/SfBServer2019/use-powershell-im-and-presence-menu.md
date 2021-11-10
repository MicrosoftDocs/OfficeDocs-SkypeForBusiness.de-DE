---
title: Verwenden von PowerShell für Aufgaben im Chat- und Anwesenheitsmenü
ms.reviewer: ''
ms.author: ankum
author: ankum
manager: ravrao
ms.date: 11/03/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: 'Zusammenfassung: Skype for Business Server Systemsteuerung zur Cmdlet-Zuordnung für das Chat- und Anwesenheitsmenü.'
ms.openlocfilehash: 9d57e249fb839894454c05d25e78320153d4a306
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2021
ms.locfileid: "60888755"
---
# <a name="im-and-presence"></a>Sofortnachrichten und Anwesenheit

In diesem Artikel wird beschrieben, wie ähnliche Ergebnisse wie die des Menüelements "Chat und **Anwesenheit"** in der älteren Systemsteuerung mithilfe von Cmdlets erzielt werden können.

In diesem Artikel werden die folgenden Untermenüs beschrieben:

- [Chat und Anwesenheit](#im-and-presence)
  - [Dateifilter](#file-filter)
  - [URL-Filter](#url-filter)

## <a name="file-filter"></a>Dateifilter

Das Untermenü **"DATEIFILTER"** ermöglicht Administratoren das Verwalten von Dateiübertragungsfilterkonfigurationen in der Organisation. Diese Konfigurationen werden verwendet, um die Möglichkeit eines Benutzers zum Übertragen bestimmter Dateitypen (z. B. Dateien mit einer VBS- oder .ps1-Dateierweiterung) mithilfe eines Skype for Business Server Clients zu blockieren.

Betrachten wir die verschiedenen Aufgaben, die ein Benutzer mit **FILE FILTER** ausführen kann, und die Skype for Business Cmdlets, denen diese Aufgaben zugeordnet sind.

---

> **Szenario 1:** Auflisten aller Dateifilter

   ![Listendateifilter](./media/file-filter-1.png)

***Cmdlet***

[Get-CsFileTransferFilterConfiguration](/powershell/module/skype/get-csfiletransferfilterconfiguration)

***Beispiel***

```powershell
 Get-CsFileTransferFilterConfiguration
```

---

> **Szenario 2:** Erstellen eines neuen Dateifilters

   ![Erstellen eines Dateifilters](./media/file-filter-2.png)

***Cmdlet***

[New-CsFileTransferFilterConfiguration](/powershell/module/skype/new-csfiletransferfilterconfiguration)  

***Beispiel***

```powershell
 New-CsFileTransferFilterConfiguration -Identity site:Redmond
```

---

> **Szenario 3:** Abrufen von Details eines ausgewählten Dateifilters

   ![Dateifilter abrufen](./media/file-filter-3.png)

***Cmdlet***

[Get-CsFileTransferFilterConfiguration](/powershell/module/skype/get-csfiletransferfilterconfiguration)

***Beispiel***

```powershell
 Get-CsFileTransferFilterConfiguration -Identity site:Redmond
```

---

> **Szenario 4:** Löschen ausgewählter Dateifilter

   ![Löschen des Dateifilters](./media/file-filter-4.png)

***Cmdlet***

[Remove-CsFileTransferFilterConfiguration](/powershell/module/skype/remove-csfiletransferfilterconfiguration)

***Beispiel***

```powershell
 Remove-CsFileTransferFilterConfiguration -Identity site:Redmond
```

---

> **Szenario 5:** Aktualisieren eines Dateifilters

   ![Dateifilter aktualisieren](./media/file-filter-5.png)

***Cmdlet***

[Set-CsFileTransferFilterConfiguration](/powershell/module/skype/set-csfiletransferfilterconfiguration)

***Beispiel***

```powershell
 Set-CsFileTransferFilterConfiguration -Identity site:Redmond -Extensions @{Add=".ps1"}
```

---

## <a name="url-filter"></a>URL-Filter

Das **Untermenüelement "URL-FILTER"** unter **"Chat und Anwesenheit"** ermöglicht Administratoren das Konfigurieren des URL-Filters, sodass Hyperlinks mit bestimmten Präfixen blockiert oder nicht aktiv sind. (Mit anderen Worten, die Teilnehmer können nicht einfach auf den Link klicken und zu der Website wechseln, auf die sich der URI bezieht. Sie müssen den Link kopieren und manuell in einen Browser einfügen.)

Betrachten wir die verschiedenen Aufgaben, die ein Benutzer mit **URL-FILTER** ausführen kann, und die Skype for Business Cmdlets, denen diese Aufgaben zugeordnet sind.

---
> **Szenario 1:** Auflisten aller Web-URL-Filter

   ![Listen-URL-Filter](./media/url-filter-1.png)

***Cmdlet***

[Get-CsImFilterConfiguration](/powershell/module/skype/get-csimfilterconfiguration)

***Beispiel***

```powershell
 Get-CsImFilterConfiguration
```

---

> **Szenario 2:** Erstellen eines neuen URL-Filters

   ![Neuer URL-Filter](./media/url-filter-2.png)

***Cmdlet***

[New-CsImFilterConfiguration](/powershell/module/skype/new-csimfilterconfiguration)  

***Beispiel***

```powershell
 New-CsImFilterConfiguration -Identity site:Redmond
```

---

> **Szenario 3:** Abrufen von Details eines ausgewählten URL-Filters

   ![URL-Filter abrufen](./media/url-filter-3.png)

***Cmdlet***

[Get-CsImFilterConfiguration](/powershell/module/skype/get-csimfilterconfiguration)

***Beispiel***

```powershell
 Get-CsImFilterConfiguration -Identity site:Redmond
```

---

> **Szenario 4:** Löschen ausgewählter URL-Filter

   ![URL-Filter löschen](./media/url-filter-4.png)

***Cmdlet***

[Remove-CsImFilterConfiguration](/powershell/module/skype/remove-csimfilterconfiguration)

***Beispiel***

```powershell
 Remove-CsImFilterConfiguration -Identity site:Redmond
```

---

> **Szenario 5:** Aktualisieren eines URL-Filters

   ![URL-Filter aktualisieren](./media/url-filter-5.png)

***Cmdlet***

[Set-CsImFilterConfiguration](/powershell/module/skype/set-csimfilterconfiguration)

***Beispiel***

```powershell
 Set-CsImFilterConfiguration -Identity site:Redmond -Enabled $False
```

---
