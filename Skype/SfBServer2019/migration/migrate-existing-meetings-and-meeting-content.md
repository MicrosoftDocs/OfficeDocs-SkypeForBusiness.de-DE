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
description: 'Wenn ein Benutzerkonto von einem Skype for Business Server 2019-Server verschoben wird, werden die folgenden Informationen mit diesem Benutzerkonto verschoben:'
ms.openlocfilehash: e28cbce30608672d27578cfaa5ab92dbe1ed3c4cd6b234da7389b1f9a6978350
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312293"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Migrieren vorhandener Besprechungen und Besprechungsinhalte

Wenn ein Benutzerkonto auf einen Skype for Business Server 2019-Server verschoben wird, werden die folgenden Informationen mit diesem Benutzerkonto verschoben:
  
- **Vom Benutzer bereits geplante Besprechungen**: Dies beinhaltet das Verschieben von Konferenzverzeichnissen und Konferenzdaten.
    
- **Persönliche Identifikationsnummer (PIN) des Benutzers.** Die aktuelle PIN des Benutzers funktioniert weiterhin, bis sie abläuft oder der Benutzer eine neue PIN anfordert.
    
Die folgenden Benutzerkontoinformationen werden nicht auf den neuen Server verschoben:
  
- **Besprechungsinhalt**. Verwenden Sie den Parameter **"-MoveConferenceData"** als Teil des **Cmdlets "Move-CsUser",** um die während einer Besprechung freigegebenen Inhalte wie PowerPoint, Whiteboard, Anlagen oder Abrufdaten zu verschieben. 
    

