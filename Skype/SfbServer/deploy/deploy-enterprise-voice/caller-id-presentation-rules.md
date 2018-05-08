---
title: Erstellen oder Ändern einer Übersetzungsregel für die Darstellung der Anrufer-ID in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: 'Zusammenfassung: Informationen Sie zum Konfigurieren der Anrufer-ID mithilfe der Skype für Business Server-Systemsteuerung.'
ms.openlocfilehash: cd4d11be6c24cc6ba092de4655e5d0b9530c3ac8
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server-2015"></a><span data-ttu-id="20f0b-103">Erstellen oder Ändern einer Übersetzungsregel für die Darstellung der Anrufer-ID in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="20f0b-103">Create or modify a translation rule for caller ID presentation in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="20f0b-104">**Zusammenfassung:** Informationen Sie zum Konfigurieren der Anrufer-ID mithilfe der Skype für Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="20f0b-104">**Summary:** Learn how to configure Caller ID by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="20f0b-105">Mit Skype für Business Server Telefonnummer des angerufenen (d. h., die Telefonnummer genannt) aus dem e. 164-Format übersetzt werden kann, um die lokale Wählformat, die durch den _trunkpeer_ (d. h., die zugehörigen Gateway, private Branch Exchange (erforderlich ist PBX) oder SIP-Trunk).</span><span class="sxs-lookup"><span data-stu-id="20f0b-105">With Skype for Business Server, the called party's phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the  _trunk peer_ (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="20f0b-106">Dazu müssen Sie eine oder mehrere Übersetzungsregeln definieren, um den Anforderungs-URI vor dem Routen an den Trunkpeer zu übersetzen.</span><span class="sxs-lookup"><span data-stu-id="20f0b-106">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>
  
<span data-ttu-id="20f0b-107">Skype für Business Server haben Sie auch die Möglichkeit, auch die Rufnummer des Anrufers (d. h., die Telefonnummer, die der Aufrufer den Aufruf ausführt) übersetzen aus dem e. 164-Format an das lokale Wählformat, das durch den trunkpeer erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="20f0b-107">Skype for Business Server also gives you the option to also translate the calling party's phone number (that is, the phone number that the caller is calling from) from E.164 format to the local dialing format that is required by the trunk peer.</span></span> <span data-ttu-id="20f0b-108">So können Sie zum Beispiel eine Übersetzungsregel schreiben, die die Angabe „+44“ am Beginn einer Wählzeichenfolge entfernt und durch „0144“ ersetzt.</span><span class="sxs-lookup"><span data-stu-id="20f0b-108">For example, you can write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>
  
### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="20f0b-109">So konfigurieren Sie die Anrufer-ID mithilfe von Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="20f0b-109">To configure Caller ID by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="20f0b-110">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="20f0b-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="20f0b-111">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Trunkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="20f0b-111">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
    
3. <span data-ttu-id="20f0b-112">Doppelklicken Sie auf der Seite **Trunkkonfiguration** auf einen vorhandenen Trunk (z. B. auf den Trunk **Global**), um das Dialogfeld **Trunkkonfiguration bearbeiten** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="20f0b-112">On the **Trunk Configuration** page, double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
4. <span data-ttu-id="20f0b-113">So konfigurieren Sie die Rufnummernanzeige:</span><span class="sxs-lookup"><span data-stu-id="20f0b-113">To configure caller ID presentation:</span></span>
    
   - <span data-ttu-id="20f0b-114">Um eine oder mehrere Regeln aus einer Liste mit allen Übersetzungsregeln in Ihrer Bereitstellung von Enterprise-VoIP verfügbar auszuwählen, klicken Sie auf **auswählen**.</span><span class="sxs-lookup"><span data-stu-id="20f0b-114">To choose one or more rules from a list of all translation rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="20f0b-115">Klicken Sie in **Übersetzungsregeln für die wählende Nummer** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="20f0b-115">In **Calling number translation rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
   - <span data-ttu-id="20f0b-116">Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="20f0b-116">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="20f0b-117">Ausführliche Informationen zum Definieren einer neuen Regel finden Sie unter [Defining Translation Rules](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="20f0b-117">For details about defining a new rule, see [Defining Translation Rules](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>
    
   - <span data-ttu-id="20f0b-118">Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die dem Trunk bereits zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="20f0b-118">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="20f0b-119">Weitere Informationen hierzu finden Sie unter [Defining Translation Rules](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="20f0b-119">For details, see [Defining Translation Rules](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>
    
   - <span data-ttu-id="20f0b-120">Wenn Sie eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel verwenden möchten, klicken Sie auf den Regelnamen, auf **Kopieren** und anschließend auf **Einfügen**.</span><span class="sxs-lookup"><span data-stu-id="20f0b-120">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="20f0b-121">Weitere Informationen hierzu finden Sie unter [Defining Translation Rules](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).</span><span class="sxs-lookup"><span data-stu-id="20f0b-121">For details, see [Defining Translation Rules](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).</span></span> 
    
   - <span data-ttu-id="20f0b-122">Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="20f0b-122">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="20f0b-123">Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den beiden Regeln Konflikte auftreten könnten.</span><span class="sxs-lookup"><span data-stu-id="20f0b-123">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span> 
  

