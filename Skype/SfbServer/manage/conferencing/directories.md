---
title: Erstellen von Konferenzverzeichnissen in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 'Zusammenfassung: Informationen zum Erstellen von Konferenzverzeichnissen in Skype for Business Server.'
ms.openlocfilehash: 6a7b8d110f06b089f166fc6ff2eb35ae35632370
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828135"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a>Erstellen von Konferenzverzeichnissen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Konferenzverzeichnissen in Skype for Business Server erstellen.
  
Konferenzverzeichnissen verwalten eine Zuordnung zwischen der alphanumerischen Besprechungs-ID, die ein Teilnehmer verwendet, um bei Verwendung von Skype for Business an einer Konferenz teil zu nehmen, und der numerischen Konferenz-ID, die ein Einwahlkonferenzteilnehmer zum Beitreten zur Konferenz verwendet. 
  
## <a name="create-a-conference-directory"></a>Erstellen eines Konferenzverzeichnisses

Indem mehrere Konferenzverzeichnisse erstellt werden, wird sichergestellt, dass Konferenz-IDs kurz bleiben, solange keine sehr große Anzahl Konferenzen erstellt wurde. 
  
Um etwa sechsstellige Konferenz-IDs zu erhalten, wird in einer Organisation mit einer typischen Konferenzanzahl pro Benutzer empfohlen, pro 999 Benutzer im Pool je ein Konferenzverzeichnis zu erstellen. Anhand dieser Richtlinie können die Konferenz-IDs im Allgemeinen klein gehalten werden. Wenn die Anzahl der Konferenzverzeichnissen (in den Pools) jedoch 9 überschreitet, wird die Konferenz-ID-Länge größer, um zusätzliche Konferenzen zu unterstützen.
  
Das Format einer Konferenz-ID lautet wie folgt: 
  
```console
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

Verwenden Sie zum Erstellen eines Konferenzverzeichnisses **das Cmdlet "New-CsConferenceDirectory".** Mit dem folgenden Befehl wird beispielsweise ein Konferenzverzeichnis mit der Identität 42 erstellt, das im Pool gehostet atl-cs-001.litwareinc.com:
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

Weitere Informationen finden Sie unter [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).
  

