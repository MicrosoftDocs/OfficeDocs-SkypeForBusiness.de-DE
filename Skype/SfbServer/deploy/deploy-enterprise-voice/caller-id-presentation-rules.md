---
title: Erstellen oder Ändern einer Übersetzungsregel für die Anrufer-ID-Präsentation in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Rufnummernanzeige mithilfe des Skype for Business Server-Control Panels konfigurieren.'
ms.openlocfilehash: ca35b3398732296f435196ffeb38d915472b303d
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233767"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="1a837-103">Erstellen oder Ändern einer Übersetzungsregel für die Anrufer-ID-Präsentation in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1a837-103">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="1a837-104">**Zusammenfassung:** Erfahren Sie, wie Sie die Rufnummernanzeige mithilfe des Skype for Business Server-Control Panels konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1a837-104">**Summary:** Learn how to configure Caller ID by using the Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="1a837-105">Mit Skype for Business Server kann die Telefonnummer des angerufenen (also die Telefonnummer) aus dem E. 164-Format in das lokale Wählformat übersetzt werden, das vom _trunk-Peer_ (also dem zugehörigen Gateway, der privaten Niederlassungs Börse) benötigt wird ( PBX) oder SIP Trunk).</span><span class="sxs-lookup"><span data-stu-id="1a837-105">With Skype for Business Server, the called party's phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the  _trunk peer_ (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="1a837-106">Dazu müssen Sie eine oder mehrere Übersetzungsregeln definieren, um den Anforderungs-URI vor dem Routen an den Trunkpeer zu übersetzen.</span><span class="sxs-lookup"><span data-stu-id="1a837-106">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<span data-ttu-id="1a837-107">Skype for Business Server bietet Ihnen auch die Möglichkeit, die Telefonnummer des Anrufers (also die Telefonnummer, von der der Anrufer anruft) vom E. 164-Format in das lokale Wählformat zu übersetzen, das vom trunk-Peer benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="1a837-107">Skype for Business Server also gives you the option to also translate the calling party's phone number (that is, the phone number that the caller is calling from) from E.164 format to the local dialing format that is required by the trunk peer.</span></span> <span data-ttu-id="1a837-108">So können Sie zum Beispiel eine Übersetzungsregel schreiben, die die Angabe „+44“ am Beginn einer Wählzeichenfolge entfernt und durch „0144“ ersetzt.</span><span class="sxs-lookup"><span data-stu-id="1a837-108">For example, you can write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1a837-109">So konfigurieren Sie die Rufnummernanzeige mithilfe der Skype for Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="1a837-109">To configure Caller ID by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="1a837-110">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="1a837-110">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="1a837-111">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Trunkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="1a837-111">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

3. <span data-ttu-id="1a837-112">Doppelklicken Sie auf der Seite **Trunkkonfiguration** auf einen vorhandenen Trunk (z. B. auf den Trunk **Global**), um das Dialogfeld **Trunkkonfiguration bearbeiten** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="1a837-112">On the **Trunk Configuration** page, double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

4. <span data-ttu-id="1a837-113">So konfigurieren Sie die Rufnummernanzeige:</span><span class="sxs-lookup"><span data-stu-id="1a837-113">To configure caller ID presentation:</span></span>

   - <span data-ttu-id="1a837-114">Wenn Sie eine oder mehrere Regeln aus einer Liste aller Übersetzungen auswählen möchten, die in Ihrer Enterprise-VoIP-Bereitstellung verfügbar sind, klicken Sie auf **auswählen**.</span><span class="sxs-lookup"><span data-stu-id="1a837-114">To choose one or more rules from a list of all translation rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="1a837-115">Klicken Sie in **Übersetzungsregeln für die wählende Nummer** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1a837-115">In **Calling number translation rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

   - <span data-ttu-id="1a837-116">Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="1a837-116">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="1a837-117">Details zum Definieren einer neuen Regel finden Sie unter [Definieren von Übersetzungsregeln](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="1a837-117">For details about defining a new rule, see  [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>

   - <span data-ttu-id="1a837-p105">Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die dem Trunk bereits zugeordnet ist. Ausführliche Informationen finden Sie unter [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="1a837-p105">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**. For details, see [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>

   - <span data-ttu-id="1a837-p106">Um eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel zu verwenden, klicken Sie auf den Regelnamen, auf **Kopieren** und anschließend auf **Einfügen**. Ausführliche Informationen finden Sie unter [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).</span><span class="sxs-lookup"><span data-stu-id="1a837-p106">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**. For details, see [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).</span></span>

   - <span data-ttu-id="1a837-122">Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="1a837-122">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="1a837-123">Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den beiden Regeln Konflikte auftreten könnten.</span><span class="sxs-lookup"><span data-stu-id="1a837-123">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>


