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
localization_priority: Normal
description: 'Wenn ein Benutzerkonto von auf einen Skype for Business Server 2019-Server verschoben wird, werden die folgenden Informationen mit diesem Benutzerkonto verschoben:'
ms.openlocfilehash: 6513f581f55028ec28d4cf05f1f1b3df37c49e65
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752687"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Migrieren vorhandener Besprechungen und Besprechungsinhalte

Wenn ein Benutzerkonto auf einen Skype for Business Server 2019-Server verschoben wird, werden die folgenden Informationen mit diesem Benutzerkonto verschoben:
  
- **Besprechungen, die bereits vom Benutzer geplant wurden**. Dies umfasst das Verschieben von Konferenz Verzeichnissen und Konferenzdaten.
    
- **Die persönliche Identifikationsnummer (PIN) des Benutzers**. Die aktuelle PIN des Benutzers bleibt so lange funktionsfähig, bis er abläuft oder der Benutzer eine neue PIN anfordert.
    
Die folgenden Benutzerkontoinformationen werden nicht auf den neuen Server verschoben:
  
- **Besprechungsinhalt**. Verwenden Sie den **-MoveConferenceData-** Parameter als Teil des Cmdlets " **CsUser** ", um die während einer Besprechung freigegebenen Inhalte wie PowerPoint, Whiteboard, Anlagen oder abrufdaten zu verlagern. 
    

