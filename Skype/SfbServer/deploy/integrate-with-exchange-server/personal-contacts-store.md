---
title: Konfigurieren des persönlichen Kontaktspeichers auf lync 2010-Clientcomputern
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 'Zusammenfassung: Konfigurieren des persönlichen Kontaktspeichers, der von Legacyclients verwendet wird.'
ms.openlocfilehash: ba9cb7ee485f94162a642f8e877213a7bcd47c55
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278084"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a>Konfigurieren des persönlichen Kontaktspeichers auf lync 2010-Clientcomputern
  
Wenn Sie Skype for Business Server 2015 und Exchange Server 2016 oder Exchange Server 2013 integrieren, sollten Sie den von den Clients verwendeten persönlichen Kontaktspeicher konfigurieren. Insbesondere sollten Sie Skype for Business so konfigurieren, dass Exchange als persönlicher Kontaktspeicher verwendet wird, und gleichzeitig sicherstellen, dass die Benutzer diese Entscheidung nicht außer Kraft setzen können. Dies ist nur dann möglich, wenn Sie auf jedem Clientcomputer einen Registrierungswert erstellen und konfigurieren.
  
> [!NOTE]
> Das folgende Verfahren ist nur für Clients notwendig, die den lync 2010-Client oder eine frühere Version verwenden. Der lync 2013-Client und alle Skype for Business-Clients haben nicht die Möglichkeit, die Einstellungen des Kontaktspeichers zu überschreiben.
  
Zum Konfigurieren dieses Werts auf einem einzelnen Computer führen Sie die folgenden Schritte aus:
  
1. Klicken Sie auf dem Clientcomputer im Menü **Start** auf **Ausführen**.
2. Geben Sie im Dialogfeld **Ausführen** den Befehl regedit ein und drücken Sie dann die EINGABETASTE.
3. Erweitern Sie im Registrierungs-Editor **HKEY_LOCAL_MACHINE**, dann **Software**, dann **Policies**, dann **Microsoft** und dann **Communicator**.
4. Klicken Sie mit der rechten Maustaste auf **Communicator**, zeigen Sie auf **Neu** und klicken Sie auf **DWORD-Wert (32-Bit)**.
5. Geben Sie nach dem Erstellen des neuen Werts PersonalContactStoreOverride ein und drücken Sie die EINGABETASTE, um den Wert umzubenennen.
6. Stellen Sie sicher, dass der Wert von PersonalContactStoreOverride 0 ist, und schließen Sie dann den Registrierungs-Editor.

Wenn Sie die gleiche Änderung auf mehreren Computern durchführen müssen, können Sie dazu ein benutzerdefiniertes Gruppenrichtlinienobjekt erstellen. Ausführliche Informationen hierzu finden Sie unter [Erstellen eines Gruppenrichtlinienobjekt](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) -Artikels in Windows 10.
  
