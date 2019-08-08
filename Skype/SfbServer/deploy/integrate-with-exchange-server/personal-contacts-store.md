---
title: Konfigurieren des persönlichen Kontaktspeichers auf lync 2010-Clientcomputern
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 'Zusammenfassung: Konfigurieren des persönlichen Kontaktspeichers, der von Legacyclients verwendet wird.'
ms.openlocfilehash: 26352517ea31b5556784f6f1ea8d1ce661cfe184
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244192"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a><span data-ttu-id="911d8-103">Konfigurieren des persönlichen Kontaktspeichers auf lync 2010-Clientcomputern</span><span class="sxs-lookup"><span data-stu-id="911d8-103">Configure the personal contacts store on Lync 2010 client computers</span></span>
  
<span data-ttu-id="911d8-104">Wenn Sie Skype for Business Server 2015 und Exchange Server 2016 oder Exchange Server 2013 integrieren, sollten Sie den von den Clients verwendeten persönlichen Kontaktspeicher konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="911d8-104">If you are integrating Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, then you should configure the personal contact store used by the clients.</span></span> <span data-ttu-id="911d8-105">Insbesondere sollten Sie Skype for Business so konfigurieren, dass Exchange als persönlicher Kontaktspeicher verwendet wird, und gleichzeitig sicherstellen, dass die Benutzer diese Entscheidung nicht außer Kraft setzen können.</span><span class="sxs-lookup"><span data-stu-id="911d8-105">In particular, you should configure Skype for Business to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="911d8-106">Dies ist nur dann möglich, wenn Sie auf jedem Clientcomputer einen Registrierungswert erstellen und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="911d8-106">This can be done by creating and configuring a Registry value on each client computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="911d8-107">Das folgende Verfahren ist nur für Clients notwendig, die den lync 2010-Client oder eine frühere Version verwenden.</span><span class="sxs-lookup"><span data-stu-id="911d8-107">The following procedure is only necessary for clients using the Lync 2010 client or earlier.</span></span> <span data-ttu-id="911d8-108">Der lync 2013-Client und alle Skype for Business-Clients haben nicht die Möglichkeit, die Einstellungen des Kontaktspeichers zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="911d8-108">The Lync 2013 client and all Skype for Business clients will not have the option of overriding the contact store settings.</span></span>
  
<span data-ttu-id="911d8-109">Zum Konfigurieren dieses Werts auf einem einzelnen Computer führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="911d8-109">To configure this value on a single computer, complete the following procedure:</span></span>
  
1. <span data-ttu-id="911d8-110">Klicken Sie auf dem Clientcomputer im Menü **Start** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="911d8-110">On the client computer, click **Start** and then click **Run**.</span></span>
2. <span data-ttu-id="911d8-111">Geben Sie im Dialogfeld **Ausführen** den Befehl regedit ein und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="911d8-111">In the **Run** dialog box, type regedit and then press ENTER.</span></span>
3. <span data-ttu-id="911d8-112">Erweitern Sie im Registrierungs-Editor **HKEY_LOCAL_MACHINE**, dann **Software**, dann **Policies**, dann **Microsoft** und dann **Communicator**.</span><span class="sxs-lookup"><span data-stu-id="911d8-112">In Registry Editor, expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>
4. <span data-ttu-id="911d8-113">Klicken Sie mit der rechten Maustaste auf **Communicator**, zeigen Sie auf **Neu** und klicken Sie auf **DWORD-Wert (32-Bit)**.</span><span class="sxs-lookup"><span data-stu-id="911d8-113">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>
5. <span data-ttu-id="911d8-114">Geben Sie nach dem Erstellen des neuen Werts PersonalContactStoreOverride ein und drücken Sie die EINGABETASTE, um den Wert umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="911d8-114">After the new value is created, type PersonalContactStoreOverride and then press ENTER to rename the value.</span></span>
6. <span data-ttu-id="911d8-115">Stellen Sie sicher, dass der Wert von PersonalContactStoreOverride 0 ist, und schließen Sie dann den Registrierungs-Editor.</span><span class="sxs-lookup"><span data-stu-id="911d8-115">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>

<span data-ttu-id="911d8-116">Wenn Sie die gleiche Änderung auf mehreren Computern durchführen müssen, können Sie dazu ein benutzerdefiniertes Gruppenrichtlinienobjekt erstellen.</span><span class="sxs-lookup"><span data-stu-id="911d8-116">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="911d8-117">Ausführliche Informationen hierzu finden Sie unter [Erstellen eines Gruppenrichtlinienobjekt](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) -Artikels in Windows 10.</span><span class="sxs-lookup"><span data-stu-id="911d8-117">For details on doing this in Windows 10, see the [Create a Group Policy Object](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) article.</span></span>
  
