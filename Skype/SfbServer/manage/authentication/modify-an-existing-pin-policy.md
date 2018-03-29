---
title: Ändern einer vorhandenen PIN-Richtlinie in Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 517caaee-3349-4fa6-8d86-e4da3258a445
description: 'Zusammenfassung: Ändern einer vorhandenen PIN-Richtlinie in Skype für Business Server 2015.'
ms.openlocfilehash: bb9be5807da0e72dfbc59d2000af82b181bfc6d6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="modify-an-existing-pin-policy-in-skype-for-business-server-2015"></a><span data-ttu-id="5f69f-103">Ändern einer vorhandenen PIN-Richtlinie in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5f69f-103">Modify an existing PIN policy in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5f69f-104">**Zusammenfassung:** Ändern einer vorhandenen PIN-Richtlinie in Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5f69f-104">**Summary:** Modify an existing PIN policy in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="5f69f-105">Die Registerkarte **PIN-Richtlinie** können Sie die Nummer persönliche Identifikationsnummer (PIN)-Authentifizierung für Benutzer bereit, die eine Verbindung Skype für Unternehmen mit IP-Telefonen herstellen.</span><span class="sxs-lookup"><span data-stu-id="5f69f-105">You can use the **PIN Policy** tab to provide personal identification number (PIN) authentication to users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="5f69f-106">Stellen Sie zur Verwendung der PIN-Authentifizierung sicher, dass in den Webdiensteinstellungen die Option **PIN-Authentifizierung aktivieren** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="5f69f-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="5f69f-107">Führen Sie die folgenden Schritte aus, um eine PIN-Richtlinie auf Benutzer- oder Standortebene zu ändern.</span><span class="sxs-lookup"><span data-stu-id="5f69f-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-modify-an-existing-pin-policy"></a><span data-ttu-id="5f69f-108">So ändern Sie eine vorhandene PIN-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="5f69f-108">To modify an existing PIN policy</span></span>

1.  <span data-ttu-id="5f69f-109">Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist 2015.</span><span class="sxs-lookup"><span data-stu-id="5f69f-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="5f69f-110">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5f69f-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="5f69f-111">Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **PIN-Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="5f69f-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="5f69f-112">Klicken Sie auf der Seite **PIN-Richtlinie** auf eine Richtlinie, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="5f69f-112">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="5f69f-p102">Geben Sie unter **PIN-Richtlinie bearbeiten** im Feld **PIN-Mindestlänge** die gewünschte Mindestlänge für die PIN ein oder wählen Sie sie aus. In der Standardeinstellung beträgt die Mindestlänge fünf Ziffern.</span><span class="sxs-lookup"><span data-stu-id="5f69f-p102">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
6. <span data-ttu-id="5f69f-p103">Aktivieren Sie das Kontrollkästchen **Maximale Anzahl von Anmeldeversuchen angeben**, um anzugeben, nach wie vielen erfolglosen Anmeldeversuchen ein Benutzer gesperrt wird. Wenn Sie diese Option nicht aktivieren, wird die maximale Anzahl von Anmeldeversuchen basierend auf der PIN-Länge automatisch festgelegt. In der Standardeinstellung wird die maximale Anzahl von Anmeldeversuchen automatisch festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5f69f-p103">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
7. <span data-ttu-id="5f69f-118">Wenn Sie das Kontrollkästchen **Maximale Anzahl von Anmeldeversuchen angeben** aktiviert haben, geben Sie in **Maximale Anzahl von Anmeldeversuchen** die maximale Anzahl von Anmeldeversuchen ein, die Sie zulassen möchten. Sie können auch einen Wert auswählen.</span><span class="sxs-lookup"><span data-stu-id="5f69f-118">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
8. <span data-ttu-id="5f69f-p104">Aktivieren Sie das Kontrollkästchen **PIN-Ablauf aktivieren**, um eine PIN-Ablaufdauer festzulegen. Wenn Sie diese Option nicht aktivieren, laufen PINs nie ab. In der Standardeinstellung ist für PINs kein Ablauf festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5f69f-p104">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
9. <span data-ttu-id="5f69f-122">Wenn Sie das Kontrollkästchen **PIN-Ablauf aktivieren** aktiviert haben, geben Sie unter **PIN-Ablauf nach (Tagen)** die Anzahl von Tagen ein, nach der PINs ablaufen.</span><span class="sxs-lookup"><span data-stu-id="5f69f-122">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
10. <span data-ttu-id="5f69f-p105">Geben Sie unter **PIN-Verlaufszähler** die Anzahl von PINs ein, die ein Benutzer erstellen muss, bevor eine PIN erneut verwendet werden kann. In der Standardeinstellung können Benutzer ihre PINs erneut verwenden.</span><span class="sxs-lookup"><span data-stu-id="5f69f-p105">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
11. <span data-ttu-id="5f69f-p106">Aktivieren Sie das Kontrollkästchen **Allgemeine Muster zulassen**, um allgemeine Muster in PINs zuzulassen, beispielsweise aufeinanderfolgende und wiederholte Zahlen. Wenn Sie diese Option nicht aktivieren, sind nur komplexe Ziffernmuster zulässig. In der Standardeinstellung dürfen nur komplexe Ziffernmuster verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5f69f-p106">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5f69f-128">Es wird empfohlen, die Verwendung gängiger Muster nicht zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="5f69f-128">We recommend that you do not allow common patterns.</span></span> 
  
12. <span data-ttu-id="5f69f-129">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="5f69f-129">Click **Commit**.</span></span>
    

