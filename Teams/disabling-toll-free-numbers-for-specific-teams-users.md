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
ms.openlocfilehash: 158a4b31b0aaf65414af0d2119b3b6931a1f74ac
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014693"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>Deaktivieren von gebührenfreien Telefonnummern für bestimmte Microsoft Teams-Benutzer

Wenn die Microsoft-Audiokonferenzbrücke Ihrer Organisation gebührenfreie Telefonnummern enthält, können Sie die Verwendung dieser Nummern in den Besprechungen bestimmter Organisatoren zulassen oder verhindern.  

Standardmäßig werden alle Benutzer in Ihrer Organisation aktiviert, für die Verwendung von gebührenfreier Nummern, was bedeutet, dass diese Nummern, falls verfügbar, von Teilnehmern verwendet werden können an einer Besprechung teilnehmen. Wenn dies nicht das gewünschte Verhalten für einige Benutzer in Ihrer Organisation ist, können Sie bestimmte Benutzer einschränken, verwenden Sie diese Nummern in ihre Besprechungen über eine gebührenfreie Nummern Aktivierung-Steuerelement. 

Wenn gebührenfreie Telefonnummern für einen bestimmten Organisator deaktiviert sind, gilt Folgendes: 
 - Die Besprechungseinladungen dieses Benutzers enthalten keine gebührenfreie Telefonnummer mehr. 
 - Gebührenfreie Telefonnummern werden nicht mehr auf der Seite „Lokale Rufnummer suchen“ aufgelistet, auf die in den Besprechungseinladungen dieses Benutzers verwiesen wird. 
 - Teilnehmer können nicht an der Besprechung des entsprechenden Organisators teilnehmen, wenn sie eine gebührenfreie Telefonnummer der Organisation wählen. 
 - Alle Besprechungen des Organisators werden automatisch neu geplant, und die gebührenfreie Telefonnummer wird aus den Besprechungen entfernt.  

    > [!IMPORTANT]
    > Dies bedeutet, dass alle E-Mail-Einladungen des Organisators erneut an die Teilnehmer dieser Besprechungen gesendet werden. 

 - Die Teilnehmer können weiterhin über gebührenpflichtige Telefonnummern an den Besprechungen des Organisators teilnehmen. 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Deaktivieren von gebührenfreien Telefonnummern für bestimmte Benutzer 

1. Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer in der Liste der verfügbaren Benutzer aus.

2. Klicken Sie oben auf der Seite auf **Bearbeiten**.

3. Klicken Sie neben **Audiokonferenz** auf **Bearbeiten**.

4. Deaktivieren Sie **Include toll-free numbers in meeting requests from this user** (Gebührenfreie Telefonnummern in Besprechungsanfragen von diesem Benutzer einschließen). 

5. Klicken Sie auf **Speichern**. 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
**Verwenden von PowerShell**  

Weitere Informationen finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
