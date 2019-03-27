---
title: Konfigurieren Sie den Speicher für persönliche Kontakte auf Lync 2010-Client-Computern
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/29/2019
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 'Zusammenfassung: Konfigurieren des persönlichen kontaktspeichers von Legacyclients verwendet.'
ms.openlocfilehash: 4afb40f57043988768118a0b83c0afe7e9df0028
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887778"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a>Konfigurieren Sie den Speicher für persönliche Kontakte auf Lync 2010-Client-Computern
  
Wenn Sie Skype für Business Server 2015 und Exchange Server 2016 oder Exchange Server 2013 integrieren, sollten Sie den persönlichen Kontaktspeicher, die von den Clients verwendeten konfigurieren. Insbesondere sollten Sie Skype für Unternehmen Exchange als den persönlichen Kontaktspeicher verwenden und gleichzeitig, stellen Sie sicher, dass Benutzer nicht diese Entscheidung überschreiben können konfigurieren. Dies ist nur dann möglich, wenn Sie auf jedem Clientcomputer einen Registrierungswert erstellen und konfigurieren.
  
> [!NOTE]
> Das folgende Verfahren ist nur erforderlich für Clients mit Lync 2010-Client oder eine frühere Version. Lync 2013-Client und alle Skype für Business-Clients müssen nicht die Möglichkeit, die Kontaktspeicher Einstellungen überschreiben.
  
Zum Konfigurieren dieses Werts auf einem einzelnen Computer führen Sie die folgenden Schritte aus:
  
1. Klicken Sie auf dem Clientcomputer im Menü **Start** auf **Ausführen**.
2. Geben Sie im Dialogfeld **Ausführen** den Befehl regedit ein und drücken Sie dann die EINGABETASTE.
3. Erweitern Sie im Registrierungs-Editor **HKEY_LOCAL_MACHINE**, dann **Software**, dann **Policies**, dann **Microsoft** und dann **Communicator**.
4. Klicken Sie mit der rechten Maustaste auf **Communicator**, zeigen Sie auf **Neu** und klicken Sie auf **DWORD-Wert (32-Bit)**.
5. Geben Sie nach dem Erstellen des neuen Werts PersonalContactStoreOverride ein und drücken Sie die EINGABETASTE, um den Wert umzubenennen.
6. Stellen Sie sicher, dass der Wert von PersonalContactStoreOverride 0 ist, und schließen Sie dann den Registrierungs-Editor.

Wenn Sie die gleiche Änderung auf mehreren Computern durchführen müssen, können Sie dazu ein benutzerdefiniertes Gruppenrichtlinienobjekt erstellen. Einzelheiten hierzu in Windows 10 finden Sie im Artikel [Erstellen eines Gruppenrichtlinienobjekts](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) .
  
