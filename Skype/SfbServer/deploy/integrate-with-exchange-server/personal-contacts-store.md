---
title: Konfigurieren des persönlichen Kontaktspeichers auf Lync 2010-Clientcomputern
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 'Zusammenfassung: Konfigurieren Des persönlichen Kontaktspeichers, der von Legacyclients verwendet wird.'
ms.openlocfilehash: 5f2131fd1e960e658d4257f0c86dd61a241aa499
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109671"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a>Konfigurieren des persönlichen Kontaktspeichers auf Lync 2010-Clientcomputern
  
Wenn Sie Skype for Business Server 2015 und Exchange Server 2016 oder Exchange Server 2013 integrieren, sollten Sie den von den Clients verwendeten persönlichen Kontaktspeicher konfigurieren. Insbesondere sollten Sie Skype for Business so konfigurieren, dass Exchange als persönlicher Kontaktspeicher verwendet wird, und gleichzeitig sicherstellen, dass Benutzer diese Entscheidung nicht außer Kraft setzen können. Dies kann durch Erstellen und Konfigurieren eines Registrierungswerts auf jedem Clientcomputer geschehen.
  
> [!NOTE]
> Das folgende Verfahren ist nur für Clients erforderlich, die den Lync 2010-Client oder früher verwenden. Der Lync 2013-Client und alle Skype for Business-Clients haben nicht die Möglichkeit, die Kontaktspeichereinstellungen außer Kraft zu setzen.
  
Zum Konfigurieren dieses Werts auf einem einzelnen Computer führen Sie die folgenden Schritte aus:
  
1. Klicken Sie auf dem Clientcomputer **auf Start** und dann auf **Ausführen**.
2. Geben Sie **im** Dialogfeld Ausführen regedit ein, und drücken Sie dann die EINGABETASTE.
3. Erweitern Sie im Registrierungs-Editor **HKEY_LOCAL_MACHINE**, erweitern **Sie Software**, erweitern Sie **Richtlinien**, erweitern **Sie Microsoft**, und erweitern Sie dann **Communicator**.
4. Klicken Sie mit **der rechten Communicator**, zeigen Sie auf **Neu**, und klicken Sie dann auf **DWORD (32-Bit)-Wert**.
5. Geben Sie nach dem Erstellen des neuen Werts PersonalContactStoreOverride ein, und drücken Sie die EINGABETASTE, um den Wert umzubenennen.
6. Stellen Sie sicher, dass der Wert von PersonalContactStoreOverride 0 ist, und schließen Sie dann den Registrierungs-Editor.

Wenn Sie die gleiche Änderung auf mehreren Computern durchführen müssen, können Sie dazu ein benutzerdefiniertes Gruppenrichtlinienobjekt erstellen. Weitere Informationen dazu in Windows 10 finden Sie im [Artikel Erstellen eines Gruppenrichtlinienobjekts.](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
