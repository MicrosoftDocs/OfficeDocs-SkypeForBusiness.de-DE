---
title: Aktivieren Sie Gruppe aufrufen Pickup-für Benutzer, und weisen Sie eine Gruppe Zahl in Skype für Unternehmen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Aktivieren von Benutzern für die Gruppe aufrufen Pickup-in Skype für Business Server Enterprise-VoIP, und weisen Sie eine Gruppennummer.
ms.openlocfilehash: 92429e256a222d56ad7c281db57185b497f714e5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892461"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>Aktivieren Sie Gruppe aufrufen Pickup-für Benutzer, und weisen Sie eine Gruppe Zahl in Skype für Unternehmen

Aktivieren von Benutzern für die Gruppe aufrufen Pickup-in Skype für Business Server Enterprise-VoIP, und weisen Sie eine Gruppennummer.

Nachdem Sie die orbittabelle für das Parken von Anrufen Rufnummern pickup-Gruppe hinzufügen, verwenden Sie das SEFAUtil-Tool, um Benutzer die Gruppennummern zugewiesen, und aktivieren für diese Gruppe aufrufen Pickup-.

> [!NOTE]
> Weisen Sie in einer hybridbereitstellung einer Gruppe anrufen Pickup-Gruppe nicht für Benutzer, die online verwaltet werden. Benutzer, die online verwaltet werden können nicht in der Gruppe anrufen Pickup-teilnehmen. Das heißt, ihre Anrufe können nicht von anderen Benutzern angenommen werden und sie können die Anrufe anderer Benutzer nicht entgegennehmen.

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>Zuweisen einer Gruppennummer und Gruppe aufrufen Pickup-für einen Benutzer aktivieren

1. Melden Sie sich mit Administratorrechten an dem Computer an, auf dem Sie das SEFAUtil-Tool installiert haben.

2. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:

   ```
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    Mit diesem Befehl können Sie beispielsweise einem Benutzer die Gruppennummer 199 zuweisen:

   ```
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a>Siehe auch

[Disable Group Pickup for Users](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

