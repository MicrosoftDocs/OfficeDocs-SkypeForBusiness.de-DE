---
title: 'Lync Server 2013: Manuelles Erstellen oder Ändern einer Übersetzungsregel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule manually
ms:assetid: 049d1db3-af58-48c5-be89-52e1d068a4bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398099(v=OCS.15)
ms:contentKeyID: 48183276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 372b394619a83ec01ca7a36bac4037c815f09fc1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757889"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-manually-in-lync-server-2013"></a><span data-ttu-id="a0d59-102">Manuelles Erstellen oder Ändern einer Übersetzungsregel in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0d59-102">Create or modify a translation rule manually in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0d59-103">_**Letztes Änderungsdatum des Themas:** 2012-08-06_</span><span class="sxs-lookup"><span data-stu-id="a0d59-103">_**Topic Last Modified:** 2012-08-06_</span></span>

<span data-ttu-id="a0d59-104">Führen Sie die folgenden Schritte aus, wenn Sie eine Übersetzungsregel definieren möchten, indem Sie einen regulären Ausdruck für das Übereinstimmungsmuster und die Übersetzungsregel schreiben.</span><span class="sxs-lookup"><span data-stu-id="a0d59-104">Follow these steps if you want to define a translation rule by writing a regular expression for the matching pattern and translation rule.</span></span> <span data-ttu-id="a0d59-105">Sie können auch eine Reihe von Werten im Tool zum **Erstellen einer Übersetzungsregel** eingeben und die lync Server-Systemsteuerung aktivieren, um das entsprechende Übereinstimmungsmuster und die entsprechende Übersetzungsregel für Sie zu generieren.</span><span class="sxs-lookup"><span data-stu-id="a0d59-105">Alternatively, you can enter a set of values in the **Build a Translation Rule** tool and enable Lync Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="a0d59-106">Ausführliche Informationen finden Sie unter [erstellen oder Ändern einer Übersetzungsregel mithilfe des Tools zum Erstellen einer Übersetzungsregel in lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).</span><span class="sxs-lookup"><span data-stu-id="a0d59-106">For details, see [Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).</span></span>

<div>

## <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="a0d59-107">So definieren Sie eine Übersetzungsregel manuell</span><span class="sxs-lookup"><span data-stu-id="a0d59-107">To define a translation rule manually</span></span>

1.  <span data-ttu-id="a0d59-108">Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an.</span><span class="sxs-lookup"><span data-stu-id="a0d59-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="a0d59-109">Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="a0d59-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="a0d59-110">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a0d59-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a0d59-111">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a0d59-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a0d59-112">Wenn Sie mit dem Definieren einer Übersetzungsregel beginnen möchten, führen Sie die Schritte unter [Konfigurieren eines Trunks mit medienumgehung in lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) bis Schritt 10 aus, oder [Konfigurieren Sie einen trunk ohne medienumgehung in lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) bis Schritt 9.</span><span class="sxs-lookup"><span data-stu-id="a0d59-112">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through step 9.</span></span>

4.  <span data-ttu-id="a0d59-113">Geben Sie im Feld **Name** auf der Seite **Neue Übersetzungsregel** oder **Übersetzungsregel bearbeiten** einen Namen ein, der das zu übersetzende Nummernmuster beschreibt.</span><span class="sxs-lookup"><span data-stu-id="a0d59-113">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

5.  <span data-ttu-id="a0d59-114">(Optional) Geben Sie unter **Beschreibung** eine Beschreibung der Übersetzungsregel ein, z. B. **US International long-distance dialing**.</span><span class="sxs-lookup"><span data-stu-id="a0d59-114">(Optional) In **Description**, type a description of the translation rule, for example **US International long-distance dialing**.</span></span>

6.  <span data-ttu-id="a0d59-115">Klicken Sie im unteren Bereich des Abschnitts **Übersetzungsregel erstellen** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="a0d59-115">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

7.  <span data-ttu-id="a0d59-116">Geben Sie unter **Regulären Ausdruck eingeben** Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a0d59-116">Enter the following in **Type a Regular Expression**:</span></span>
    
      - <span data-ttu-id="a0d59-117">Geben Sie unter **Übereinstimmung mit dem folgenden Muster** das Muster an, das für den Abgleich der zu übersetzenden Nummern verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a0d59-117">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>
    
      - <span data-ttu-id="a0d59-118">Geben Sie unter **Übersetzungsregel** ein Muster für das Format der übersetzten Nummern an.</span><span class="sxs-lookup"><span data-stu-id="a0d59-118">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>
    
    <span data-ttu-id="a0d59-119">Wenn Sie beispielsweise \*\* ^ \\+\\(d{9}\\+) $\*\* in **Übereinstimmung mit diesem Muster** und **011 $1** in der **Übersetzungsregel**eingeben, wird die Regel + 441235551010 in 011441235551010 übersetzen.</span><span class="sxs-lookup"><span data-stu-id="a0d59-119">For example, if you enter **^\\+(\\d{9}\\d+)$** in **Match this pattern** and **011$1** in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

8.  <span data-ttu-id="a0d59-120">Klicken Sie auf **OK**, um die Übersetzungsregel zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a0d59-120">Click **OK** to save the translation rule.</span></span>

9.  <span data-ttu-id="a0d59-121">Klicken Sie auf **OK**, um die Trunkkonfiguration zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a0d59-121">Click **OK** to save the trunk configuration.</span></span>

10. <span data-ttu-id="a0d59-122">Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit** und klicken Sie anschließend auf **Commit für alle Elemente ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a0d59-122">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a0d59-123">Immer dann, wenn Sie eine Übersetzungsregel erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit für alle Elemente ausführen</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="a0d59-123">Whenever you create or modify a translation rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="a0d59-124">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="a0d59-124">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a0d59-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0d59-125">See Also</span></span>


[<span data-ttu-id="a0d59-126">Erstellen oder Ändern einer Übersetzungsregel mithilfe des Tools zum Erstellen einer Übersetzungsregel in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0d59-126">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
[<span data-ttu-id="a0d59-127">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0d59-127">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="a0d59-128">Konfigurieren eines Trunks ohne medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0d59-128">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[<span data-ttu-id="a0d59-129">Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0d59-129">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="a0d59-130">Globale Medien Umgehungs Optionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0d59-130">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

