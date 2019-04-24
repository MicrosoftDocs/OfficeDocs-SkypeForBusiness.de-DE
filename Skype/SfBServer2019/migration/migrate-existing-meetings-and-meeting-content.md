---
title: Migrieren vorhandener Besprechungen und Besprechungsinhalte
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Wenn ein Benutzerkonto aus an einen Skype für Business Server 2019 Server verschoben wird, werden die folgende Informationen zusammen mit dem Benutzerkonto verschoben:'
ms.openlocfilehash: bf10fa6b4ad4d555ce80dee5ec4e4a6584020ac7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231658"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Migrieren vorhandener Besprechungen und Besprechungsinhalte

Wenn ein Benutzerkonto in ein Skype für Business Server 2019 Server verschoben wird, werden die folgende Informationen zusammen mit dem Benutzerkonto verschoben:
  
- **Vom Benutzer bereits geplante Besprechungen**. Dazu gehören die konferenzverzeichnisse und Konferenzdaten verschieben.
    
- **Persönliche Identifikationsnummer (PIN) des Benutzers**. Aktuelle PIN des Benutzers ist weiterhin solange gültig, bis sie abläuft oder der Benutzer eine neue PIN anfordert.
    
Die folgenden Benutzerkontoinformationen werden nicht auf dem neuen Server verschoben.
  
- **Der Inhalt der Besprechung**. Zum Verschieben des Inhalts während einer Besprechung freigegeben wie PowerPoint, Whiteboard, Anlagen oder Umfrage-Daten den **MoveConferenceData -** Parameter als Teil der **Move-CsUser** -Cmdlet verwenden. 
    

