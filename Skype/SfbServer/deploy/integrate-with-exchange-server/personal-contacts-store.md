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
# <a name="configure-the-personal-contacts-store-on-client-computers-for-skype-for-business-server"></a><span data-ttu-id="450e0-103">Konfigurieren Sie den Speicher für persönliche Kontakte auf den Clientcomputern für Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="450e0-103">Configure the personal contacts store on client computers for Skype for Business Server</span></span>
 
<span data-ttu-id="450e0-104">**Zusammenfassung:** Konfigurieren Sie den persönlichen Kontaktspeicher von Exchange Server 2016 oder Exchange Server 2013 und Skype für Business Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="450e0-104">**Summary:** Configure the personal contact store used by Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>
  
<span data-ttu-id="450e0-105">Wenn Sie Skype für Business Server und Exchange Server 2016 oder Exchange Server 2013 integrieren, sollten Sie den persönlichen Kontaktspeicher auf allen Computern unter Skype für Unternehmen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="450e0-105">If you are integrating Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, then you should configure the personal contact store on any client computers running Skype for Business.</span></span> <span data-ttu-id="450e0-106">Insbesondere sollten Sie Skype für Unternehmen Exchange als den persönlichen Kontaktspeicher verwenden und gleichzeitig, stellen Sie sicher, dass Benutzer nicht diese Entscheidung überschreiben können konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="450e0-106">In particular, you should configure Skype for Business to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="450e0-107">Dies ist nur dann möglich, wenn Sie auf jedem Clientcomputer einen Registrierungswert erstellen und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="450e0-107">This can be done by creating and configuring a Registry value on each client computer.</span></span>
  
<span data-ttu-id="450e0-108">Beachten Sie, dass dies nicht auf Computern mit Skype für Unternehmen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="450e0-108">Note that this is not required on computers running Skype for Business.</span></span>
  
<span data-ttu-id="450e0-109">Zum Konfigurieren dieses Werts auf einem einzelnen Computer führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="450e0-109">To configure this value on a single computer, complete the following procedure:</span></span>
  
1. <span data-ttu-id="450e0-110">Klicken Sie auf dem Clientcomputer im Menü **Start** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="450e0-110">On the client computer, click **Start** and then click **Run**.</span></span>
    
2. <span data-ttu-id="450e0-111">Geben Sie im Dialogfeld **Ausführen** den Befehl regedit ein und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="450e0-111">In the **Run** dialog box, type regedit and then press ENTER.</span></span>
    
3. <span data-ttu-id="450e0-112">Erweitern Sie im Registrierungs-Editor **HKEY_LOCAL_MACHINE**, dann **Software**, dann **Policies**, dann **Microsoft** und dann **Communicator**.</span><span class="sxs-lookup"><span data-stu-id="450e0-112">In Registry Editor, expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>
    
4. <span data-ttu-id="450e0-113">Klicken Sie mit der rechten Maustaste auf **Communicator**, zeigen Sie auf **Neu** und klicken Sie auf **DWORD-Wert (32-Bit)**.</span><span class="sxs-lookup"><span data-stu-id="450e0-113">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>
    
5. <span data-ttu-id="450e0-114">Geben Sie nach dem Erstellen des neuen Werts PersonalContactStoreOverride ein und drücken Sie die EINGABETASTE, um den Wert umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="450e0-114">After the new value is created, type PersonalContactStoreOverride and then press ENTER to rename the value.</span></span>
    
6. <span data-ttu-id="450e0-115">Stellen Sie sicher, dass der Wert von PersonalContactStoreOverride 0 ist, und schließen Sie dann den Registrierungs-Editor.</span><span class="sxs-lookup"><span data-stu-id="450e0-115">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>
    
<span data-ttu-id="450e0-116">Wenn Sie die gleiche Änderung auf mehreren Computern durchführen müssen, können Sie dazu ein benutzerdefiniertes Gruppenrichtlinienobjekt erstellen.</span><span class="sxs-lookup"><span data-stu-id="450e0-116">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="450e0-117">Weitere Informationen hierzu finden Sie in der Gruppenrichtlinien-Dokumentation unter [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?LinkId=268543).</span><span class="sxs-lookup"><span data-stu-id="450e0-117">For details, see the Group Policy documentation at [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?LinkId=268543).</span></span>
  

