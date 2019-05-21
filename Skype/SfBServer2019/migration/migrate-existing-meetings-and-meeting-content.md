---
title: Migrieren vorhandener Besprechungen und Besprechungsinhalte
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Wenn ein Benutzerkonto von einem Skype for Business Server 2019-Server verschoben wird, werden die folgenden Informationen mit diesem Benutzerkonto verschoben:'
ms.openlocfilehash: 4b5c7981374f3e2bf6dc2d87a0b21d972ddb14ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288600"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Migrieren vorhandener Besprechungen und Besprechungsinhalte

Wenn ein Benutzerkonto auf einen Skype for Business Server 2019-Server verschoben wird, werden die folgenden Informationen mit diesem Benutzerkonto verschoben:
  
- **Besprechungen, die der Benutzer bereits geplant**hat. Dazu gehören das Verschieben von Konferenz Verzeichnissen und Konferenzdaten.
    
- **Persönliche Identifikationsnummer (PIN) des Benutzers**. Die aktuelle PIN des Benutzers funktioniert weiterhin, bis er abläuft oder der Benutzer eine neue PIN anfordert.
    
Die folgenden Benutzerkontoinformationen werden nicht auf den neuen Server verschoben.
  
- **Besprechungsinhalt**. Verwenden Sie den Parameter **-MoveConferenceData** als Teil des Cmdlets **Move-CsUser** , um den während einer Besprechung freigegebenen Inhalt wie PowerPoint, Whiteboard, Anlagen oder Umfragedaten zu verschieben. 
    

