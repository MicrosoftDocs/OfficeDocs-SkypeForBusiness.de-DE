---
title: Aktivieren der Gruppenanruf Abholung für Benutzer und Zuweisen einer Gruppennummer in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Aktivieren Sie Benutzer für die Gruppenanruf Abholung in Skype for Business Server Enterprise-VoIP, und weisen Sie eine Gruppennummer zu.
ms.openlocfilehash: bebddb5f71612cf23d442366c774d0e8d4b9f500
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767268"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>Aktivieren der Gruppenanruf Abholung für Benutzer und Zuweisen einer Gruppennummer in Skype for Business

Aktivieren Sie Benutzer für die Gruppenanruf Abholung in Skype for Business Server Enterprise-VoIP, und weisen Sie eine Gruppennummer zu.

Nach dem Hinzufügen von Gruppennummern für die Anruf Abholung zur Umlaufbahn Tabelle des Anruf Parks verwenden Sie das SEFAUtil-Tool, um die Gruppennummern Benutzern zuzuweisen und die Gruppenanruf Abholung für Sie zu aktivieren.

> [!NOTE]
> Weisen Sie in einer hybridbereitstellung Benutzern, die Online sind, keine Gruppenanruf-Abhol Gruppe zu. Benutzer, die Online sind, können nicht an der Gruppenanruf Abholung teilnehmen. Das heißt, ihre Anrufe können nicht von anderen Benutzern angenommen werden und sie können die Anrufe anderer Benutzer nicht entgegennehmen.

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>So weisen Sie eine Gruppennummer zu und aktivieren die Gruppenanruf Abholung für einen Benutzer

1. Melden Sie sich mit Administratorrechten an dem Computer an, auf dem Sie das SEFAUtil-Tool installiert haben.

2. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    Mit diesem Befehl können Sie beispielsweise einem Benutzer die Gruppennummer 199 zuweisen:

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a>Siehe auch

[Disable Group Pickup for Users](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

