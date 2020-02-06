---
title: Migrieren vorhandener Besprechungen und Besprechungsinhalte
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Wenn ein Benutzerkonto von einem Skype for Business Server 2019-Server verschoben wird, werden die folgenden Informationen mit diesem Benutzerkonto verschoben:'
ms.openlocfilehash: 6394ebf798560ce5a13fe7ba931076364257decc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813473"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Migrieren vorhandener Besprechungen und Besprechungsinhalte

Wenn ein Benutzerkonto auf einen Skype for Business Server 2019-Server verschoben wird, werden die folgenden Informationen mit diesem Benutzerkonto verschoben:
  
- **Besprechungen, die der Benutzer bereits geplant**hat. Dazu gehören das Verschieben von Konferenz Verzeichnissen und Konferenzdaten.
    
- **Persönliche Identifikationsnummer (PIN) des Benutzers**. Die aktuelle PIN des Benutzers funktioniert weiterhin, bis er abläuft oder der Benutzer eine neue PIN anfordert.
    
Die folgenden Benutzerkontoinformationen werden nicht auf den neuen Server verschoben.
  
- **Besprechungsinhalt**. Verwenden Sie den Parameter **-MoveConferenceData** als Teil des Cmdlets **Move-CsUser** , um den während einer Besprechung freigegebenen Inhalt wie PowerPoint, Whiteboard, Anlagen oder Umfragedaten zu verschieben. 
    

