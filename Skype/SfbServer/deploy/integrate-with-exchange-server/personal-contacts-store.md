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
description: 'Zusammenfassung: Konfigurieren des persönlichen Kontaktspeichers, der von Legacyclients verwendet wird.'
ms.openlocfilehash: 66ef1c3726ea020669894769b48b2313e1da2e0e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833935"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a>Konfigurieren des persönlichen Kontaktspeichers auf Lync 2010-Clientcomputern
  
Wenn Sie Skype for Business Server 2015 und Exchange Server 2016 oder Exchange Server 2013 integrieren, sollten Sie den von den Clients verwendeten persönlichen Kontaktspeicher konfigurieren. Insbesondere sollten Sie Skype for Business für die Verwendung von Exchange als persönlichen Kontaktspeicher konfigurieren und gleichzeitig sicherstellen, dass Benutzer diese Entscheidung nicht außer Kraft setzen können. Dazu können Sie auf jedem Clientcomputer einen Registrierungswert erstellen und konfigurieren.
  
> [!NOTE]
> Das folgende Verfahren ist nur für Clients erforderlich, die den Lync 2010-Client oder eine frühere Version verwenden. Der Lync 2013-Client und alle Skype for Business-Clients haben nicht die Möglichkeit, die Kontaktspeichereinstellungen außer Kraft zu setzen.
  
Zum Konfigurieren dieses Werts auf einem einzelnen Computer führen Sie die folgenden Schritte aus:
  
1. Klicken Sie auf dem Clientcomputer auf **"Start"** und dann auf **"Ausführen".**
2. Geben Sie **im Dialogfeld** Ausführen regedit ein, und drücken Sie dann die EINGABETASTE.
3. Erweitern Sie im **Registrierungs-Editor HKEY_LOCAL_MACHINE**, erweitern **Sie "Software",**"Richtlinien", **"Microsoft"** und dann **Communicator**. 
4. Klicken Sie mit **der Communicator**, zeigen Sie auf **"Neu",** und klicken Sie dann auf **"DWORD-Wert" (32-Bit).**
5. Geben Sie nach dem Erstellen des neuen Werts PersonalContactStoreOverride ein, und drücken Sie die EINGABETASTE, um den Wert umzubenennen.
6. Stellen Sie sicher, dass der Wert von PersonalContactStoreOverride 0 ist, und schließen Sie dann den Registrierungs-Editor.

Wenn Sie die gleiche Änderung auf mehreren Computern durchführen müssen, können Sie dazu ein benutzerdefiniertes Gruppenrichtlinienobjekt erstellen. Weitere Informationen dazu in Windows 10 finden Sie im Artikel zum Erstellen [eines Gruppenrichtlinienobjekts.](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
  
