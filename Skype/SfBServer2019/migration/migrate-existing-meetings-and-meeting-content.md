---
title: Migrieren Sie vorhandener Besprechungen und Besprechungsinhalten
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Wenn ein Benutzerkonto aus an einen Skype für Business Server 2019 Server verschoben wird, werden die folgende Informationen zusammen mit dem Benutzerkonto verschoben:'
ms.openlocfilehash: 03ccad0498af777c7d93765af7df2baf5da51f83
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030371"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Migrieren Sie vorhandener Besprechungen und Besprechungsinhalten

Wenn ein Benutzerkonto in ein Skype für Business Server 2019 Server verschoben wird, werden die folgende Informationen zusammen mit dem Benutzerkonto verschoben:
  
- **Vom Benutzer bereits geplante Besprechungen**. Dazu gehören die konferenzverzeichnisse und Konferenzdaten verschieben.
    
- **Persönliche Identifikationsnummer (PIN) des Benutzers**. Aktuelle PIN des Benutzers ist weiterhin solange gültig, bis sie abläuft oder der Benutzer eine neue PIN anfordert.
    
Die folgenden Benutzerkontoinformationen werden nicht auf dem neuen Server verschoben.
  
- **Der Inhalt der Besprechung**. Zum Verschieben des Inhalts während einer Besprechung freigegeben wie PowerPoint, Whiteboard, Anlagen oder Umfrage-Daten den **MoveConferenceData -** Parameter als Teil der **Move-CsUser** -Cmdlet verwenden. 
    

