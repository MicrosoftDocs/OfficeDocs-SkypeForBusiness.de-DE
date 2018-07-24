---
title: Konfigurieren Sie den Speicher für persönliche Kontakte auf den Clientcomputern für Skype für Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 'Zusammenfassung: Konfigurieren des persönlichen kontaktspeichers von Exchange Server 2016 oder Exchange Server 2013 und Skype für Business Server verwendet.'
ms.openlocfilehash: 311bab825412bae79c240ddb0f923c693b97103e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21012900"
---
# <a name="configure-the-personal-contacts-store-on-client-computers-for-skype-for-business-server"></a>Konfigurieren Sie den Speicher für persönliche Kontakte auf den Clientcomputern für Skype für Business Server
 
**Zusammenfassung:** Konfigurieren Sie den persönlichen Kontaktspeicher von Exchange Server 2016 oder Exchange Server 2013 und Skype für Business Server verwendet.
  
Wenn Sie Skype für Business Server und Exchange Server 2016 oder Exchange Server 2013 integrieren, sollten Sie den persönlichen Kontaktspeicher auf allen Computern unter Skype für Unternehmen konfigurieren. Insbesondere sollten Sie Skype für Unternehmen Exchange als den persönlichen Kontaktspeicher verwenden und gleichzeitig, stellen Sie sicher, dass Benutzer nicht diese Entscheidung überschreiben können konfigurieren. Dies ist nur dann möglich, wenn Sie auf jedem Clientcomputer einen Registrierungswert erstellen und konfigurieren.
  
Beachten Sie, dass dies nicht auf Computern mit Skype für Unternehmen erforderlich ist.
  
Zum Konfigurieren dieses Werts auf einem einzelnen Computer führen Sie die folgenden Schritte aus:
  
1. Klicken Sie auf dem Clientcomputer im Menü **Start** auf **Ausführen**.
    
2. Geben Sie im Dialogfeld **Ausführen** den Befehl regedit ein und drücken Sie dann die EINGABETASTE.
    
3. Erweitern Sie im Registrierungs-Editor **HKEY_LOCAL_MACHINE**, dann **Software**, dann **Policies**, dann **Microsoft** und dann **Communicator**.
    
4. Klicken Sie mit der rechten Maustaste auf **Communicator**, zeigen Sie auf **Neu** und klicken Sie auf **DWORD-Wert (32-Bit)**.
    
5. Geben Sie nach dem Erstellen des neuen Werts PersonalContactStoreOverride ein und drücken Sie die EINGABETASTE, um den Wert umzubenennen.
    
6. Stellen Sie sicher, dass der Wert von PersonalContactStoreOverride 0 ist, und schließen Sie dann den Registrierungs-Editor.
    
Wenn Sie die gleiche Änderung auf mehreren Computern durchführen müssen, können Sie dazu ein benutzerdefiniertes Gruppenrichtlinienobjekt erstellen. Weitere Informationen hierzu finden Sie in der Gruppenrichtlinien-Dokumentation unter [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?LinkId=268543).
  

