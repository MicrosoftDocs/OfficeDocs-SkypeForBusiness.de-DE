---
title: Migrieren vorhandener Besprechungen und Besprechungsinhalte
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 'Wenn ein Benutzerkonto von einem Skype for Business Server 2019-Server verschoben wird, werden die folgenden Informationen mit diesem Benutzerkonto verschoben:'
ms.openlocfilehash: 826b511250e46e2c87720a5b074b43cd545b15c6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589301"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Migrieren vorhandener Besprechungen und Besprechungsinhalte

Wenn ein Benutzerkonto auf einen Skype for Business Server 2019-Server verschoben wird, werden die folgenden Informationen mit diesem Benutzerkonto verschoben:
  
- **Vom Benutzer bereits geplante Besprechungen**: Dies beinhaltet das Verschieben von Konferenzverzeichnissen und Konferenzdaten.
    
- **Persönliche Identifikationsnummer (PIN) des Benutzers.** Die aktuelle PIN des Benutzers funktioniert weiterhin, bis sie abläuft oder der Benutzer eine neue PIN anfordert.
    
Die folgenden Benutzerkontoinformationen werden nicht auf den neuen Server verschoben:
  
- **Besprechungsinhalt**. Um die während einer Besprechung freigegebenen Inhalte zu verschieben, z. B. PowerPoint, Whiteboard, Anlagen oder Abrufdaten, verwenden Sie den Parameter **"-MoveConferenceData"** als Teil des **Cmdlets "Move-CsUser".** 
    

