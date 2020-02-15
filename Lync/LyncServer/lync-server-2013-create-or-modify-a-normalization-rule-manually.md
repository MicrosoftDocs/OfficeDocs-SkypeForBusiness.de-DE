---
title: 'Lync Server 2013: Manuelles Erstellen oder Ändern einer Normalisierungsregel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule manually
ms:assetid: fc0335e6-8830-4cfb-8c64-6aeb98c0a992
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413074(v=OCS.15)
ms:contentKeyID: 48185943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 305369719631361e0e8f8d9e9d12101fbdbfb1e5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045928"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-manually-in-lync-server-2013"></a><span data-ttu-id="69079-102">Manuelles Erstellen oder Ändern einer Normalisierungsregel in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69079-102">Create or modify a normalization rule manually in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69079-103">_**Letztes Änderungsstand des Themas:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="69079-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="69079-104">Führen Sie die folgenden Schritte aus, wenn Sie eine Normalisierungsregel manuell erstellen oder ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="69079-104">Complete the following steps if you want to create or modify a normalization rule manually.</span></span> <span data-ttu-id="69079-105">Wenn Sie eine Normalisierungsregel mithilfe von Create a normalize Rule in lync Server-Systemsteuerung erstellen oder ändern möchten, finden Sie weitere Informationen unter [erstellen oder Ändern einer Normalisierungsregel mithilfe von Create a normalize Rule in lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md).</span><span class="sxs-lookup"><span data-stu-id="69079-105">If you want to create or modify a normalization rule by using Build a Normalization Rule in Lync Server Control Panel, see [Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md).</span></span>

<div>

## <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="69079-106">So definieren Sie eine Normalisierungsregel manuell</span><span class="sxs-lookup"><span data-stu-id="69079-106">To define a normalization rule manually</span></span>

1.  <span data-ttu-id="69079-107">Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an.</span><span class="sxs-lookup"><span data-stu-id="69079-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="69079-108">Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="69079-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="69079-109">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="69079-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="69079-110">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="69079-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="69079-111">Optional Führen Sie die Schritte unter [Create a Dial Plan in lync Server 2013](lync-server-2013-create-a-dial-plan.md) oder [Modify a Dial Plan in lync Server 2013](lync-server-2013-modify-a-dial-plan.md)aus.</span><span class="sxs-lookup"><span data-stu-id="69079-111">(Optional) Follow the steps in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) or [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

4.  <span data-ttu-id="69079-112">Geben Sie unter **neue Normalisierungsregel** oder **Normalisierungsregel bearbeiten**einen Namen ein, der das im **Namen** normalisierte Nummernmuster beschreibt (beispielsweise den Namen Normalisierungsregel **5DigitExtension**).</span><span class="sxs-lookup"><span data-stu-id="69079-112">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule **5DigitExtension**).</span></span>

5.  <span data-ttu-id="69079-113">Optional Geben Sie im Feld **Beschreibung** eine Beschreibung der Normalisierungsregel ein (beispielsweise "übersetzt 5-stellige Durchwahlnummern").</span><span class="sxs-lookup"><span data-stu-id="69079-113">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

6.  <span data-ttu-id="69079-114">Klicken Sie in **Normalisierungsregel erstellen**auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="69079-114">In **Build a Normalization Rule**, click **Edit**.</span></span>

7.  <span data-ttu-id="69079-115">Geben Sie in **Regulären Ausdruck eingeben** Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="69079-115">Enter the following in **Type a Regular Expression**:</span></span>
    
      - <span data-ttu-id="69079-116">Geben Sie unter **dieses Muster abgleichen**das Muster an, das Sie für die Übereinstimmung mit der gewählten Telefonnummer verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="69079-116">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>
    
      - <span data-ttu-id="69079-117">Geben Sie in **Übersetzungsregel**ein Muster für das Format der übersetzten E. 164-Telefonnummern an.</span><span class="sxs-lookup"><span data-stu-id="69079-117">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>
    
    <span data-ttu-id="69079-118">Wenn Sie beispielsweise **^\\(d{7}) $** in **Übereinstimmung mit diesem Muster** und **+ 1425 $1** in der **Übersetzungsregel**eingeben, normalisiert die Regel 5550100 bis + 14255550100.</span><span class="sxs-lookup"><span data-stu-id="69079-118">For example, if you enter **^(\\d{7})$** in **Match this pattern** and **+1425$1** in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>

8.  <span data-ttu-id="69079-119">Optional Wenn die Normalisierungsregel eine interne Telefonnummer für Ihre Organisation ergibt, wählen Sie **interne Durchwahl**aus.</span><span class="sxs-lookup"><span data-stu-id="69079-119">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

9.  <span data-ttu-id="69079-120">Optional Geben Sie eine Zahl ein, um die Normalisierungsregel zu testen, und klicken Sie dann auf **go**.</span><span class="sxs-lookup"><span data-stu-id="69079-120">(Optional) Enter a number to test the normalization rule and then click **Go**.</span></span> <span data-ttu-id="69079-121">Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="69079-121">The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="69079-122">Sie können eine Normalisierungsregel speichern, die den Test noch nicht besteht, und Sie dann später neu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="69079-122">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="69079-123">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-test-voice-routing.md">Testen der VoIP-Weiterleitung in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="69079-123">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="69079-124">Klicken Sie auf **OK** , um die Normalisierungsregel zu speichern.</span><span class="sxs-lookup"><span data-stu-id="69079-124">Click **OK** to save the normalization rule.</span></span>

11. <span data-ttu-id="69079-125">Klicken Sie auf **OK** , um die Wähleinstellungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="69079-125">Click **OK** to save the dial plan.</span></span>

12. <span data-ttu-id="69079-126">Klicken Sie auf der Seite **Wähleinstellungen** auf **Commit** und anschließend auf **Commit für alle**.</span><span class="sxs-lookup"><span data-stu-id="69079-126">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="69079-127">Wenn Sie eine Normalisierungsregel erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit all</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="69079-127">Whenever you create or change a normalization rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="69079-128">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="69079-128">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="69079-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69079-129">See Also</span></span>


[<span data-ttu-id="69079-130">Erstellen oder Ändern einer Normalisierungsregel mithilfe der Regel zum Erstellen einer Normalisierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69079-130">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)  
[<span data-ttu-id="69079-131">Erstellen von Wähleinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69079-131">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="69079-132">Ändern von Wähleinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69079-132">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="69079-133">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69079-133">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="69079-134">Testen des VoIP-Routings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69079-134">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

