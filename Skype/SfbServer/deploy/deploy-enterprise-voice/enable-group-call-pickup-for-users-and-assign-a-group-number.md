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
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Aktivieren Sie Benutzer für die Gruppenanrufannahme in Skype for Business Server Enterprise-VoIP, und weisen Sie eine Gruppennummer zu.
ms.openlocfilehash: 2aad048c5e01e34e4503fa648fe5cac96e142690
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58614895"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>Aktivieren der Gruppenanrufannahme für Benutzer und Zuweisen einer Gruppennummer in Skype for Business

Aktivieren Sie Benutzer für die Gruppenanrufannahme in Skype for Business Server Enterprise-VoIP, und weisen Sie eine Gruppennummer zu.

Nachdem Sie der Orbittabelle für das Parken von Anrufen Gruppennummern für die Anrufannahme hinzugefügt haben, verwenden Sie das SEFAUtil-Tool, um die Gruppennummern Benutzern zuzuweisen und die Gruppenanrufannahme für sie zu aktivieren.

> [!NOTE]
> Weisen Sie in einer Hybridbereitstellung benutzern, die online verwaltet werden, keine Gruppe zur Gruppenanrufannahme zu. Online verwaltete Benutzer können nicht an der Gruppenanrufannahme teilnehmen. Das heißt, ihre Anrufe können nicht von anderen Benutzern angenommen werden, und sie können keine Anrufe an andere Benutzer annehmen.

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>So weisen Sie eine Gruppennummer zu und aktivieren die Gruppenanrufannahme für einen Benutzer

1. Melden Sie sich bei dem Computer an, auf dem Sie das SEFAUtil-Tool mit Administratorrechten installiert haben.

2. Führen Sie an der Eingabeaufforderung Folgendes aus:

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    So weisen Sie z. B. einem Benutzer die Gruppennummer 199 zu:

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a>Siehe auch

[Deaktivieren der Gruppenannahme für Benutzer](/previous-versions/office/lync-server-2013/lync-server-2013-disable-group-call-pickup-for-users)