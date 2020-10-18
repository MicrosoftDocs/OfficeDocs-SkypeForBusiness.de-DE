---
title: Erstellen oder Ändern einer Übersetzungsregel mithilfe des Tools zum Erstellen einer Übersetzungsregel
description: Erstellen oder Ändern einer Übersetzungsregel mithilfe des Tools zum Erstellen einer Übersetzungsregel.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule by using the Build a Translation Rule tool
ms:assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412909(v=OCS.15)
ms:contentKeyID: 48185224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 116048fff834e797bca76a895f45cd0ebc83ab94
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574521"
---
# <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool-in-lync-server-2013"></a><span data-ttu-id="85ac6-103">Erstellen oder Ändern einer Übersetzungsregel mithilfe des Tools zum Erstellen einer Übersetzungsregel in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85ac6-103">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85ac6-104">_**Letztes Änderungsstand des Themas:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="85ac6-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="85ac6-105">Führen Sie die folgenden Schritte aus, wenn Sie eine Übersetzungsregel definieren möchten, indem Sie einen Wertesatz in das Tool zum **Erstellen einer Übersetzungsregel** eingeben und lync Server-Systemsteuerung das entsprechende Übereinstimmungsmuster und die Übersetzungsregel für Sie generieren.</span><span class="sxs-lookup"><span data-stu-id="85ac6-105">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Lync Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="85ac6-106">Alternativ können Sie einen regulären Ausdruck manuell schreiben, um das übereinstimmende Muster und die Übersetzungsregel zu definieren.</span><span class="sxs-lookup"><span data-stu-id="85ac6-106">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="85ac6-107">Ausführliche Informationen finden Sie unter [erstellen oder Ändern einer Übersetzungsregel manuell in lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).</span><span class="sxs-lookup"><span data-stu-id="85ac6-107">For details, see [Create or modify a translation rule manually in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).</span></span>

<div>

## <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="85ac6-108">So definieren Sie eine Regel mit dem Tool zum Erstellen einer Übersetzungsregel</span><span class="sxs-lookup"><span data-stu-id="85ac6-108">To define a rule by using the Build a Translation Rule tool</span></span>

1.  <span data-ttu-id="85ac6-109">Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an.</span><span class="sxs-lookup"><span data-stu-id="85ac6-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="85ac6-110">Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="85ac6-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="85ac6-111">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="85ac6-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="85ac6-112">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="85ac6-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="85ac6-113">Um mit der Definition einer Übersetzungsregel zu beginnen, führen Sie die Schritte unter [Configure a trunk with Media Bypass in lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through Step 10 durch, oder [Konfigurieren Sie einen trunk ohne medienumgehung in lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) bis Schritt 9.</span><span class="sxs-lookup"><span data-stu-id="85ac6-113">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through step 9.</span></span>

4.  <span data-ttu-id="85ac6-114">Geben Sie unter **Name** auf der Seite **neue Übersetzungsregel** oder **Übersetzungsregel bearbeiten** einen Namen ein, der das zu übersetzende Nummernmuster beschreibt.</span><span class="sxs-lookup"><span data-stu-id="85ac6-114">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

5.  <span data-ttu-id="85ac6-115">Optional Geben Sie unter **Beschreibung**eine Beschreibung der Übersetzungsregel ein, beispielsweise **US International Dialing**(Ferngespräche).</span><span class="sxs-lookup"><span data-stu-id="85ac6-115">(Optional) Under **Description**, type a description of the translation rule, for example **US International long-distance dialing**.</span></span>

6.  <span data-ttu-id="85ac6-116">Geben Sie im Abschnitt **Übersetzungsregel erstellen** des Dialogfelds Werte in die folgenden Felder ein:</span><span class="sxs-lookup"><span data-stu-id="85ac6-116">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>
    
      - <span data-ttu-id="85ac6-117">**Starting digits**: (optional) geben Sie die führenden Ziffern von Zahlen an, die mit dem Muster übereinstimmen sollen.</span><span class="sxs-lookup"><span data-stu-id="85ac6-117">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="85ac6-118">Geben Sie beispielsweise **+** in dieses Feldnummern im E. 164-Format (die mit + beginnen) überein.</span><span class="sxs-lookup"><span data-stu-id="85ac6-118">For example, enter **+** in this field to match numbers in E.164 format (which begin with +).</span></span>
    
      - <span data-ttu-id="85ac6-119">**Length**: Geben Sie die Anzahl der Stellen im übereinstimmenden Muster an, und wählen Sie aus, ob das Muster Zahlen entsprechen soll, die diese Länge genau, mindestens diese Länge oder eine beliebige Länge aufweisen.</span><span class="sxs-lookup"><span data-stu-id="85ac6-119">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length.</span></span> <span data-ttu-id="85ac6-120">Geben Sie beispielsweise **11** ein, und wählen Sie **mindestens** in der Dropdownliste aus, um Nummern mit einer Länge von mindestens 11 Ziffern abzugleichen.</span><span class="sxs-lookup"><span data-stu-id="85ac6-120">For example, enter **11** and select **At least** in the drop-down list to match numbers that are at least 11 digits in length.</span></span>
    
      - <span data-ttu-id="85ac6-121">**Zu entfernende Ziffern**: (optional) geben Sie die Anzahl der zu entfernenden Start Ziffern an.</span><span class="sxs-lookup"><span data-stu-id="85ac6-121">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="85ac6-122">Geben Sie beispielsweise **1** ein, um den **+** vom Anfang der Zahl zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="85ac6-122">For example, enter **1** to strip out the **+** from the beginning of the number.</span></span>
    
      - <span data-ttu-id="85ac6-123">**Hinzuzufügende Ziffern**: (optional) geben Sie Ziffern an, die den übersetzten Zahlen vorangestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="85ac6-123">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers.</span></span> <span data-ttu-id="85ac6-124">Geben Sie beispielsweise " **011** " ein, wenn Sie möchten, dass die übersetzten Nummern beim Anwenden der Regel auf "011" vorangestellt werden.</span><span class="sxs-lookup"><span data-stu-id="85ac6-124">For example, enter **011** if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>
    
    <span data-ttu-id="85ac6-125">Die in diesen Feldern eingegebenen Werte werden in den Feldern **Muster für Übereinstimmung** und **Übersetzungsregel** wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="85ac6-125">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields.</span></span> <span data-ttu-id="85ac6-126">Wenn Sie beispielsweise die obigen Beispielwerte angeben, lautet der resultierende reguläre Ausdruck im Feld **Muster an Übereinstimmung** wie folgt:</span><span class="sxs-lookup"><span data-stu-id="85ac6-126">For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>
    
    <span data-ttu-id="85ac6-127">**^\\+ ( \\ d {9} \\ d +) $**</span><span class="sxs-lookup"><span data-stu-id="85ac6-127">**^\\+(\\d{9}\\d+)$**</span></span>
    
    <span data-ttu-id="85ac6-128">Das Feld **Übersetzungsregel** gibt ein Muster für das Format der übersetzten Zahlen an.</span><span class="sxs-lookup"><span data-stu-id="85ac6-128">The **Translation rule** field specifies a pattern for the format of translated numbers.</span></span> <span data-ttu-id="85ac6-129">Dieses Muster besteht aus zwei Teilen:</span><span class="sxs-lookup"><span data-stu-id="85ac6-129">This pattern has two parts:</span></span>
    
      - <span data-ttu-id="85ac6-130">Ein Wert (beispielsweise **$1**), der die Anzahl der Stellen im übereinstimmenden Muster darstellt.</span><span class="sxs-lookup"><span data-stu-id="85ac6-130">A value (for example, **$1**) that represents the number of digits in the matching pattern</span></span>
    
      - <span data-ttu-id="85ac6-131">Optional Ein Wert, den Sie voranstellen können, indem Sie ihn in das Feld **hinzuzufügende Ziffern** eingeben</span><span class="sxs-lookup"><span data-stu-id="85ac6-131">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>
    
    <span data-ttu-id="85ac6-132">Mit den obigen Beispielwerten wird **011 $1** im **Übersetzungsregel** Feld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="85ac6-132">Using the preceding example values, **011$1** appears in the **Translation rule** field.</span></span>
    
    <span data-ttu-id="85ac6-133">Wenn diese Übersetzungsregel angewendet wird, wird + 441235551010 zu 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="85ac6-133">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

7.  <span data-ttu-id="85ac6-134">Klicken Sie auf **OK**, um die Übersetzungsregel zu speichern.</span><span class="sxs-lookup"><span data-stu-id="85ac6-134">Click **OK** to save the translation rule.</span></span>

8.  <span data-ttu-id="85ac6-135">Klicken Sie auf **OK**, um die Trunkkonfiguration zu speichern.</span><span class="sxs-lookup"><span data-stu-id="85ac6-135">Click **OK** to save the trunk configuration.</span></span>

9.  <span data-ttu-id="85ac6-136">Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit**, und klicken Sie anschließend auf **Commit für alle**.</span><span class="sxs-lookup"><span data-stu-id="85ac6-136">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="85ac6-137">Jedes Mal, wenn Sie eine Übersetzungsregel erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit für alle Elemente ausführen</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="85ac6-137">Whenever you create or modify a translation rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="85ac6-138">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="85ac6-138">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="85ac6-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85ac6-139">See Also</span></span>


[<span data-ttu-id="85ac6-140">Manuelles Erstellen oder Ändern einer Übersetzungsregel in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85ac6-140">Create or modify a translation rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
[<span data-ttu-id="85ac6-141">Konfigurieren eines Trunks mit medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85ac6-141">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="85ac6-142">Konfigurieren eines Trunks ohne medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85ac6-142">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[<span data-ttu-id="85ac6-143">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85ac6-143">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="85ac6-144">Optionen für die globale medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85ac6-144">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

