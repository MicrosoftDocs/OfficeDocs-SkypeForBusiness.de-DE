---
title: Deaktivieren von gebührenfreien Telefonnummern für bestimmte Microsoft Teams-Benutzer
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Administratoren können steuern, wie Organisatoren gebührenfreie Telefonnummern für ihre Besprechungen verwenden können.
ms.openlocfilehash: cc179ff20d3bd523952ce57a79553025092532a9
ms.sourcegitcommit: 044286f9dec2743a622bdaeac03469418cfdfa0d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/19/2018
ms.locfileid: "25678338"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>Deaktivieren von gebührenfreien Telefonnummern für bestimmte Microsoft Teams-Benutzer

Wenn die Microsoft-Audiokonferenzbrücke Ihrer Organisation gebührenfreie Telefonnummern enthält, können Sie die Verwendung dieser Nummern in den Besprechungen bestimmter Organisatoren zulassen oder verhindern.  

Standardmäßig ist die Verwendung von gebührenfreien Telefonnummern für alle Benutzer in der Organisation aktiviert. Das heißt, wenn diese Nummern verfügbar sind, können sie von Teilnehmern für die Teilnahme an den Besprechungen der Benutzer verwendet werden. Wenn dieses Verhalten für einige Benutzer in der Organisation nicht gewünscht wird, können Sie über ein Steuerelement für die Aktivierung gebührenfreier Telefonnummern festlegen, dass bestimmte Benutzer diese Nummern nicht in ihren Besprechungen verwenden können. 

Wenn gebührenfreie Telefonnummern für einen bestimmten Organisator deaktiviert sind, gilt Folgendes: 
 - Die Besprechungseinladungen dieses Benutzers enthalten keine gebührenfreie Telefonnummer mehr. 
 - Gebührenfreie Telefonnummern werden nicht mehr auf der Seite „Lokale Rufnummer suchen“ aufgelistet, auf die in den Besprechungseinladungen dieses Benutzers verwiesen wird. 
 - Teilnehmer können nicht an der Besprechung des entsprechenden Organisators teilnehmen, wenn sie eine gebührenfreie Telefonnummer der Organisation wählen. 
 - Alle Besprechungen des Organisators werden automatisch neu geplant, und die gebührenfreie Telefonnummer wird aus den Besprechungen entfernt.  

    > [!IMPORTANT]
    > Dies bedeutet, dass alle E-Mail-Einladungen des Organisators erneut an die Teilnehmer dieser Besprechungen gesendet werden. 

 - Die Teilnehmer können weiterhin über gebührenpflichtige Telefonnummern an den Besprechungen des Organisators teilnehmen. 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Deaktivieren von gebührenfreien Telefonnummern für bestimmte Benutzer 

Von der **Microsoft-Teams & Skype für Business Admin Center**:

1. Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie neben **Audiokonferenz** auf **Bearbeiten**.

3. **Gebührenfreie Nummern in Besprechungsanfragen von diesem Benutzer umfassen** auf **deaktiviert**festgelegt. 

4. Klicken Sie auf **Speichern**. 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
**Verwenden von PowerShell**  

Weitere Informationen finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
