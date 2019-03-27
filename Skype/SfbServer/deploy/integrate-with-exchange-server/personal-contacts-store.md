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
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a><span data-ttu-id="65120-103">Konfigurieren Sie den Speicher für persönliche Kontakte auf Lync 2010-Client-Computern</span><span class="sxs-lookup"><span data-stu-id="65120-103">Configure the personal contacts store on Lync 2010 client computers</span></span>
  
<span data-ttu-id="65120-104">Wenn Sie Skype für Business Server 2015 und Exchange Server 2016 oder Exchange Server 2013 integrieren, sollten Sie den persönlichen Kontaktspeicher, die von den Clients verwendeten konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="65120-104">If you are integrating Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, then you should configure the personal contact store used by the clients.</span></span> <span data-ttu-id="65120-105">Insbesondere sollten Sie Skype für Unternehmen Exchange als den persönlichen Kontaktspeicher verwenden und gleichzeitig, stellen Sie sicher, dass Benutzer nicht diese Entscheidung überschreiben können konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="65120-105">In particular, you should configure Skype for Business to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="65120-106">Dies ist nur dann möglich, wenn Sie auf jedem Clientcomputer einen Registrierungswert erstellen und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="65120-106">This can be done by creating and configuring a Registry value on each client computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="65120-107">Das folgende Verfahren ist nur erforderlich für Clients mit Lync 2010-Client oder eine frühere Version.</span><span class="sxs-lookup"><span data-stu-id="65120-107">The following procedure is only necessary for clients using the Lync 2010 client or earlier.</span></span> <span data-ttu-id="65120-108">Lync 2013-Client und alle Skype für Business-Clients müssen nicht die Möglichkeit, die Kontaktspeicher Einstellungen überschreiben.</span><span class="sxs-lookup"><span data-stu-id="65120-108">The Lync 2013 client and all Skype for Business clients will not have the option of overriding the contact store settings.</span></span>
  
<span data-ttu-id="65120-109">Zum Konfigurieren dieses Werts auf einem einzelnen Computer führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="65120-109">To configure this value on a single computer, complete the following procedure:</span></span>
  
1. <span data-ttu-id="65120-110">Klicken Sie auf dem Clientcomputer im Menü **Start** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="65120-110">On the client computer, click **Start** and then click **Run**.</span></span>
2. <span data-ttu-id="65120-111">Geben Sie im Dialogfeld **Ausführen** den Befehl regedit ein und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="65120-111">In the **Run** dialog box, type regedit and then press ENTER.</span></span>
3. <span data-ttu-id="65120-112">Erweitern Sie im Registrierungs-Editor **HKEY_LOCAL_MACHINE**, dann **Software**, dann **Policies**, dann **Microsoft** und dann **Communicator**.</span><span class="sxs-lookup"><span data-stu-id="65120-112">In Registry Editor, expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>
4. <span data-ttu-id="65120-113">Klicken Sie mit der rechten Maustaste auf **Communicator**, zeigen Sie auf **Neu** und klicken Sie auf **DWORD-Wert (32-Bit)**.</span><span class="sxs-lookup"><span data-stu-id="65120-113">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>
5. <span data-ttu-id="65120-114">Geben Sie nach dem Erstellen des neuen Werts PersonalContactStoreOverride ein und drücken Sie die EINGABETASTE, um den Wert umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="65120-114">After the new value is created, type PersonalContactStoreOverride and then press ENTER to rename the value.</span></span>
6. <span data-ttu-id="65120-115">Stellen Sie sicher, dass der Wert von PersonalContactStoreOverride 0 ist, und schließen Sie dann den Registrierungs-Editor.</span><span class="sxs-lookup"><span data-stu-id="65120-115">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>

<span data-ttu-id="65120-116">Wenn Sie die gleiche Änderung auf mehreren Computern durchführen müssen, können Sie dazu ein benutzerdefiniertes Gruppenrichtlinienobjekt erstellen.</span><span class="sxs-lookup"><span data-stu-id="65120-116">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="65120-117">Einzelheiten hierzu in Windows 10 finden Sie im Artikel [Erstellen eines Gruppenrichtlinienobjekts](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) .</span><span class="sxs-lookup"><span data-stu-id="65120-117">For details on doing this in Windows 10, see the [Create a Group Policy Object](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) article.</span></span>
  
