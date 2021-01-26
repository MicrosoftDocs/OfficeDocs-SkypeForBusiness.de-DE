---
title: Aktivieren der Gruppenanrufannahme für Benutzer und Zuweisen einer Gruppennummer in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Aktivieren Sie Benutzer für die Gruppenanrufannahme in Skype for Business Server Enterprise-VoIP, und weisen Sie eine Gruppennummer zu.
ms.openlocfilehash: 3467aea1b9671a93cca2f66a2ac73c39f15dc26e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830965"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>Aktivieren der Gruppenanrufannahme für Benutzer und Zuweisen einer Gruppennummer in Skype for Business

Aktivieren Sie Benutzer für die Gruppenanrufannahme in Skype for Business Server Enterprise-VoIP, und weisen Sie eine Gruppennummer zu.

Nachdem Sie der Orbittabelle für das Parken von Anrufen Gruppennummern für die Anrufannahme hinzugefügt haben, verwenden Sie das SEFAUtil-Tool, um die Gruppennummern Benutzern zuzuordnen und die Gruppenanrufannahme für sie zu aktivieren.

> [!NOTE]
> Weisen Sie in einer Hybridbereitstellung Benutzern, die online zu Hause sind, keine Gruppenanrufannahmegruppe zu. Benutzer, die online zu Hause sind, können nicht an der Gruppenanrufannahme teilnehmen. Das heißt, ihre Anrufe können nicht von anderen Benutzern beantwortet werden, und sie können keine Anrufe an andere Benutzer beantworten.

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>So weisen Sie eine Gruppennummer zu und aktivieren die Gruppenanrufannahme für einen Benutzer

1. Melden Sie sich bei dem Computer an, auf dem Sie das Tool SEFAUtil mit Administratorrechten installiert haben.

2. Führen Sie an der Eingabeaufforderung Folgendes aus:

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    So weisen Sie beispielsweise einem Benutzer die Gruppennummer 199 zu:

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a>Siehe auch

[Deaktivieren der Gruppenannahme für Benutzer](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

