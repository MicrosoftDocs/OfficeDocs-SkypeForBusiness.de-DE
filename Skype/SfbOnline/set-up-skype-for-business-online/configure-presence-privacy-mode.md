---
title: Konfigurieren des vertraulichen Anwesenheitsmodus
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b33d57fe-b9cf-43c1-961a-edf28db738e8
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- ms.lync.lac.OrgPresencePrivacy
description: 'Erfahren Sie, wie Sie den Datenschutzmodus für Ihre Benutzer einrichten, damit sie besser steuern können, wie Personen ihre Verfügbarkeit sehen können. '
ms.openlocfilehash: f8589dfb648693f0c0c4331a1a16119a3d7fe748
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239952"
---
# <a name="configure-presence-privacy-mode"></a>Konfigurieren des vertraulichen Anwesenheitsmodus

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> Das Microsoft Teams Admin Center wurde durch das Skype for Business Admin Center (Legacyportal) ersetzt. Alle Einstellungen für die Skype for Business befinden sich jetzt im Teams Admin Center. Ihnen muss die [Azure AD-Administratorrolle](/azure/active-directory/roles/permissions-reference) eines globalen Admins oder Skype for Business zugewiesen sein, damit Skype for Business Features im Teams Admin Center verwalten können. Weitere Informationen finden Sie unter [Verwalten Skype for Business-Einstellungen im Microsoft Teams Admin Center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).

Die Skype for Business Online-Anwesenheitseinstellung gibt Personen mehr Kontrolle darüber, wer sehen kann, ob sie verfügbar, in einer Besprechung oder nicht im Büro sind. Details zu Skype for Business Anwesenheits- und Datenschutzeinstellungen finden Sie unter Konfigurieren der [Anwesenheitsinformationen in Skype for Business Online.](configure-presence-in-skype-for-business-online.md) 
  
## <a name="choose-the-default-online-presence-setting-for-everyone-in-your-organization"></a>Wählen Sie die Standardeinstellung für Onlinepräsenzen für alle in Ihrer Organisation aus.
<a name="__top"> </a>

1. Wechseln Sie zum Skype for Business Online Admin Center > **Organisation > Allgemein.**
    
2. Wählen **Sie unter Anwesenheitsschutzmodus** die Einstellung aus, und klicken Sie dann auf **Speichern.**
    
|**Einstellung**|**Wer können die Anwesenheit eines Benutzers anzeigen**|
|:-----|:-----|
|**Anwesenheitsinformationen automatisch anzeigen** <br/> |Jeder Skype for Business-Benutzer, der nicht zu den Vertraulichkeitsgruppen **Extern** oder **Blockiert** gehört <br/> |
|**Anwesenheitsinformationen nur für die Kontakte eines Benutzers anzeigen** <br/> |Alle Personen in der Kontaktliste eines Benutzers, die nicht der Datenschutzgruppe "Extern" oder **"Blockiert"** angehören.  <br/> Einzelne Benutzer können diese Einstellung im Dialogfeld Skype for Business **Optionen** ändern. <br/> |
   
## <a name="related-topics"></a>Verwandte Themen
[Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)

[Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md)

  
