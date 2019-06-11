---
title: 'Lync Server 2013: Erstellen einer VoIP-Route'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a voice route
ms:assetid: d189057d-cc9d-4622-9d10-f5385d703faf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398898(v=OCS.15)
ms:contentKeyID: 48185438
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe4c6a9492cbbecafff95a1f6e626087e79f62d0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="dfdf3-102">Erstellen einer VoIP-Route in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfdf3-102">Create a voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfdf3-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="dfdf3-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="dfdf3-104">Im folgenden Verfahren wird erläutert, wie Sie mithilfe der lync Server 2013-Systemsteuerung eine neue VoIP-Route erstellen.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-104">The following procedure explains how to create a new voice route by using the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="dfdf3-105">Informationen zum Bearbeiten einer vorhandenen Route finden Sie unter [Ändern einer VoIP-Route in lync Server 2013](lync-server-2013-modify-a-voice-route.md) für das Verfahren.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-105">To edit an existing route, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md) for the procedure.</span></span>

<div>

## <a name="to-create-a-voice-route-by-using-the-lync-server-control-panel"></a><span data-ttu-id="dfdf3-106">So erstellen Sie eine VoIP-Route mithilfe der lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="dfdf3-106">To create a voice route by using the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="dfdf3-107">Melden Sie sich als Mitglied der Gruppe RTCUniversalServerAdmins oder als Benutzer mit der Administratorrolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** beim Computer an.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>

2.  <span data-ttu-id="dfdf3-108">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dfdf3-109">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="dfdf3-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dfdf3-110">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-110">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="dfdf3-111">Klicken Sie auf **Route**.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-111">Click **Route**.</span></span>

5.  <span data-ttu-id="dfdf3-112">Klicken Sie auf **Neu**, um das Dialogfeld **Neue VoIP-Route** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-112">Click **New** to display the **New Voice Route** dialog box.</span></span>

6.  <span data-ttu-id="dfdf3-113">Geben Sie in **Name** einen beschreibenden Namen für die VoIP-Route ein.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-113">In **Name**, type a descriptive name for the voice route.</span></span>

7.  <span data-ttu-id="dfdf3-114">(Optional) Geben Sie in **Beschreibung** zusätzliche beschreibende Informationen zur VoIP-Route ein.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-114">(Optional) In **Description**, type additional descriptive information for the voice route.</span></span>

8.  <span data-ttu-id="dfdf3-115">Zur Festlegung der Muster für diese Route können Sie entweder das Tool **Zu suchendes Muster erstellen** verwenden, um einen regulären Ausdruck zu generieren oder Sie erstellen manuell einen regulären Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-115">To specify the patterns that you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
      - <span data-ttu-id="dfdf3-p103">Geben Sie bei Verwendung des Tools **Zu suchendes Muster erstellen** zum Generieren eines regulären Ausdrucks die erforderlichen Werte wie nachfolgend beschrieben ein. Sie können zwei Arten von Mustervergleich angeben:</span><span class="sxs-lookup"><span data-stu-id="dfdf3-p103">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows. You can specify two types of pattern matching:</span></span>
        
          - <span data-ttu-id="dfdf3-118">**Anfangsziffern für Zahlen, die Sie zulassen möchten:** Geben Sie die Präfixwerte ein, die diese Route erfüllen muss (einschließlich des führenden +, falls erforderlich).</span><span class="sxs-lookup"><span data-stu-id="dfdf3-118">**Starting digits for numbers that you want to allow:** Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="dfdf3-119">Geben Sie beispielsweise **+425** ein und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-119">For example, type **+425**, and then click **Add**.</span></span> <span data-ttu-id="dfdf3-120">Wiederholen Sie diesen Schritt für jeden Präfixwert, den Sie in der Route einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-120">Repeat this for each prefix value that you want to include in the route.</span></span>
        
          - <span data-ttu-id="dfdf3-121">**Ausnahmen:** Wenn Sie eine oder mehrere Ausnahmen für einen Präfixwert angeben möchten, markieren Sie das Präfix, und klicken Sie auf **Ausnahmen**.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-121">**Exceptions:** If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="dfdf3-122">Geben Sie einen oder mehrere Werte für die übereinstimmenden Muster ein, die nicht für diese Route *geeignet* sein sollen.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-122">Type in one or more values for the matching patterns that you do *not* want this route to accommodate.</span></span> <span data-ttu-id="dfdf3-123">Wenn Sie beispielsweise Zahlen, die mit + 425237 beginnen, von der Route ausschließen möchten, geben Sie im Feld **Ausnahmen** den Wert **+ 425237** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-123">For example, to exclude numbers starting with +425237 from the route, enter a value of **+425237** in the **Exceptions** field, and then click **OK**.</span></span>
    
      - <span data-ttu-id="dfdf3-124">Wenn Sie das Muster für den Vergleich manuell definieren möchten, klicken Sie im Tool **Muster für Vergleich erstellen** auf **Bearbeiten** und geben dann einen regulären .NET Framework-Ausdruck ein, um das Muster für den Vergleich von Zieltelefonnummern anzugeben, auf die die Route angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-124">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.</span></span> <span data-ttu-id="dfdf3-125">Ausführliche Informationen zum Schreiben regulärer Ausdrücke finden Sie unter ".NET Framework-reguläre Ausdrücke" [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)unter.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-125">For details about how to write regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

9.  <span data-ttu-id="dfdf3-p107">Wählen Sie die Option **Anrufer-ID unterdrücken**, wenn Sie nicht möchten, dass dem Anrufempfänger bei ausgehenden Anrufen die Telefon-ID angezeigt wird. Wenn Sie diese Option aktivieren, müssen Sie eine **Alternative Anrufer-ID** angeben, die dem Anrufempfänger auf dem Display angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-p107">Select **Suppress caller ID** if you do not want the ID of the phone making the outbound call to appear to the call recipient. If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient’s caller ID display.</span></span>

10. <span data-ttu-id="dfdf3-128">Klicken Sie auf **Hinzufügen**, um der VoIP-Route einen oder mehrere Trunks zuzuordnen und wählen Sie aus der Liste einen Trunk aus.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-128">To associate one or more trunks with the voice route, click **Add** and then select a trunk from the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dfdf3-129">Wenn Ihre Bereitstellung alle Microsoft Office Communications Server 2007 R2-Vermittlungsserver umfasst, stehen diese auch in der Liste zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-129">If your deployment includes any Microsoft Office Communications Server 2007 R2 Mediation Servers, they will also be available in the list.</span></span>

    
    </div>

11. <span data-ttu-id="dfdf3-130">Wenn Sie eine oder mehrere PSTN-Nutzungen (Public Switched Telephone Network) mit der VoIP-Route verknüpfen möchten, klicken Sie auf **auswählen** , und wählen Sie einen Eintrag aus der Liste der PSTN-Verwendungseinträge aus, die für Ihre Enterprise-VoIP-Bereitstellung definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-130">To associate one or more public switched telephone network (PSTN) usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dfdf3-131">Informationen zum Anzeigen der Eigenschaften der einzelnen verfügbaren PSTN-Verwendungsdaten Sätze finden Sie unter <A href="lync-server-2013-view-pstn-usage-records.md">Anzeigen von PSTN-Nutzungsdaten Sätzen in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-131">To view the properties of each of the available PSTN usage records, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="dfdf3-132">Informationen zum Erstellen oder Bearbeiten von PSTN-Nutzungsdaten Sätzen finden Sie unter <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013</A> oder <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="dfdf3-132">To create or edit PSTN usage records, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="dfdf3-p108">Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Wenn Sie die Position eines Eintrags in der Liste ändern möchten, markieren Sie den Eintragsnamen und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-p108">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dfdf3-135">Im Gegensatz zu einer VoIP-Richtlinie, bei der die Reihenfolge der PSTN-Verwendungseinträge eine wichtige Rolle spielt, ist die Reihenfolge der PSTN-Verwendungseinträge in einer VoIP-Route unerheblich.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-135">In contrast to a voice policy, where the order in which PSTN usage records are listed is important, the order in which PSTN usage records are listed in the voice route is insignificant.</span></span> <span data-ttu-id="dfdf3-136">Dennoch wird empfohlen, die Liste nach Verwendungshäufigkeit zu strukturieren.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-136">However, we recommend that you organize the list by frequency of use.</span></span> <span data-ttu-id="dfdf3-137">Beispiel: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-137">For example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="dfdf3-138">(Lync Server durchläuft die Liste von oben nach unten.)</span><span class="sxs-lookup"><span data-stu-id="dfdf3-138">(Lync Server traverses the list from the top down.)</span></span>

    
    </div>

13. <span data-ttu-id="dfdf3-p110">(Optional) Geben Sie im Feld **Geben Sie eine übersetzte Nummer für den Test ein** einen Wert ein und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb des Felds angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-p110">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**. The test results are displayed under the field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dfdf3-141">Sie können eine VoIP-Route, die den Test noch nicht bestanden hat, speichern und später erneut konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-141">You can save a voice route that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="dfdf3-142">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-test-voice-routing.md">Testen des VoIP-Routings in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-142">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

14. <span data-ttu-id="dfdf3-143">Klicken Sie auf **OK**, um die VoIP-Route zu speichern.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-143">Click **OK** to save the voice route.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="dfdf3-144">Jedes Mal, wenn Sie eine VoIP-Route erstellen, müssen Sie den Befehl <STRONG>Commit für alle Elemente ausführen</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-144">Whenever you create a voice route, you must run the <STRONG>Commit All</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="dfdf3-145">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="dfdf3-145">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dfdf3-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dfdf3-146">See Also</span></span>


[<span data-ttu-id="dfdf3-147">Ändern einer VoIP-Route in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfdf3-147">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="dfdf3-148">Anzeigen von PSTN-Nutzungsdaten Sätzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfdf3-148">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="dfdf3-149">Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfdf3-149">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="dfdf3-150">Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfdf3-150">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="dfdf3-151">Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfdf3-151">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="dfdf3-152">Testen des VoIP-Routings in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfdf3-152">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

