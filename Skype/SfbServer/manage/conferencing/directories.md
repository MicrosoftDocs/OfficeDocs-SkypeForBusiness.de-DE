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
ms.openlocfilehash: e4d73cc73a5c3c343e8a4734923cf80fb2590211
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119474"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a>Erstellen von Konferenzverzeichnissen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Konferenzverzeichnissen in Skype for Business Server erstellen.
  
Konferenzverzeichnissen verwalten eine Zuordnung zwischen der alphanumerischen Besprechungs-ID, die ein Teilnehmer zum Teilnehmen an einer Konferenz verwendet, wenn skype for Business verwendet wird, und der numerischen Konferenz-ID, die ein Einwahlkonferenzteilnehmer zum Teilnehmen an der Konferenz verwendet. 
  
## <a name="create-a-conference-directory"></a>Erstellen eines Konferenzverzeichnisses

Indem mehrere Konferenzverzeichnisse erstellt werden, wird sichergestellt, dass Konferenz-IDs kurz bleiben, solange keine sehr große Anzahl Konferenzen erstellt wurde. 
  
Um etwa sechsstellige Konferenz-IDs zu erhalten, wird in einer Organisation mit einer typischen Konferenzanzahl pro Benutzer empfohlen, pro 999 Benutzer im Pool je ein Konferenzverzeichnis zu erstellen. Anhand dieser Richtlinie können die Konferenz-IDs im Allgemeinen klein gehalten werden. Wenn die Anzahl der Konferenzverzeichnissen (in den Pools) jedoch 9 überschreitet, wird die Länge der Konferenz-ID anwachsen, um zusätzliche Konferenzen zu unterstützen.
  
Das Format einer Konferenz-ID lautet wie folgt: 
  
```console
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

Verwenden Sie zum Erstellen eines Konferenzverzeichnisses **das Cmdlet New-CsConferenceDirectory.** Mit dem folgenden Befehl wird beispielsweise ein Konferenzverzeichnis mit der Identität 42 erstellt, das im Pool gehostet atl-cs-001.litwareinc.com:
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

Weitere Informationen finden Sie unter [New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps).
