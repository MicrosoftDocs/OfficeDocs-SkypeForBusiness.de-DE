---
title: Erstellen von Konferenzverzeichnissen in Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 'Zusammenfassung: Erfahren Sie, wie konferenzverzeichnisse in Skype für Business Server 2015 zu erstellen.'
ms.openlocfilehash: 861172a76da68d39fd9f8213de6e45a892aa1780
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568745"
---
# <a name="create-conference-directories-in-skype-for-business-server-2015"></a>Erstellen von Konferenzverzeichnissen in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie konferenzverzeichnisse in Skype für Business Server 2015 zu erstellen.
  
Konferenzverzeichnisse verwalten eine Zuordnung zwischen alphanumerische besprechungs-ID, die ein Teilnehmer an einer Konferenz teilnehmen, bei Verwendung von Skype für Unternehmen verwendet und die numerische Konferenz-ID, einwahlkonferenzen Teilnehmer an der Konferenz teilnehmen. 
  
## <a name="create-a-conference-directory"></a>Ein Konferenzverzeichnis erstellen

Indem mehrere Konferenzverzeichnisse erstellt werden, wird sichergestellt, dass Konferenz-IDs kurz bleiben, solange keine sehr große Anzahl Konferenzen erstellt wurde. 
  
In einer Organisation mit einer typischen Konferenzanzahl pro Nutzer wird empfohlen, pro 999 Nutzer im Pool je ein Konferenzverzeichnis zu erstellen. Wenn diese Richtlinie eingehalten wird, bleiben die Konferenz-IDs in der Regel kurz. Sobald die Anzahl der Konferenzverzeichnisse (in den Pools) 9 übersteigt, wird die Konferenz-ID-Nummer jedoch größer, um zusätzliche Konferenzen zu unterstützen.
  
Das Format einer Konferenz-ID lautet folgendermaßen: 
  
```
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

Verwenden Sie das Cmdlet **New-CsConferenceDirectory**, um ein Konferenzverzeichnis zu erstellen. So wird zum Beispiel über den folgenden Befehl ein neues Konferenzverzeichnis mit dem Identitätswert 42 erstellt, das im Pool „atl-cs-001.litwareinc.com“ gehostet wird:
  
```
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

Weitere Informationen finden Sie unter [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).
  

