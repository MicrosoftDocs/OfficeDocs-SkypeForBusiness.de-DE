---
title: 'Lync Server 2013: Ändern einer VoIP-Route'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a voice route
ms:assetid: afc562cc-8807-489b-8850-dbbe1c1ab9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412838(v=OCS.15)
ms:contentKeyID: 48185143
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0731383eea99e7510ef1748777e7139e2d9f369
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727545"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="36c70-102">Ändern einer VoIP-Route in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36c70-102">Modify a voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36c70-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="36c70-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="36c70-104">In diesem Thema wird erläutert, wie Sie eine VoIP-Route bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="36c70-104">This topic explains how to edit a voice route.</span></span> <span data-ttu-id="36c70-105">Informationen zum Erstellen einer neuen Route finden Sie unter [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="36c70-105">To create a new route, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>

<div>

## <a name="to-modify-a-voice-route"></a><span data-ttu-id="36c70-106">So ändern Sie eine VoIP-Route</span><span class="sxs-lookup"><span data-stu-id="36c70-106">To modify a voice route</span></span>

1.  <span data-ttu-id="36c70-107">Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an.</span><span class="sxs-lookup"><span data-stu-id="36c70-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="36c70-108">Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="36c70-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="36c70-109">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="36c70-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="36c70-110">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="36c70-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="36c70-111">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und klicken Sie dann auf **Route**.</span><span class="sxs-lookup"><span data-stu-id="36c70-111">In the left navigation bar, click **Voice Routing**, and then click **Route**.</span></span>

4.  <span data-ttu-id="36c70-112">Verwenden Sie auf der Seite **Route** eine der folgenden Methoden, um eine VoIP-Route zu ändern:</span><span class="sxs-lookup"><span data-stu-id="36c70-112">On the **Route** page, use either of the following methods to modify a voice route:</span></span>
    
      - <span data-ttu-id="36c70-113">Klicken Sie auf den Namen einer VoIP-Route, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="36c70-113">Click a voice route name, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="36c70-p104">Klicken Sie auf den Namen einer VoIP-Route, klicken Sie auf **Bearbeiten**, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**. Klicken Sie auf die neue Kopie der VoIP-Route, die Sie soeben erstellt haben, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="36c70-p104">Click a voice route name, click **Edit**, click **Copy**, and then click **Paste**. Click the new copy of the voice route that you just created, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="36c70-116">Geben Sie auf der Seite **VoIP-Route bearbeiten** im Feld **Name** einen beschreibenden Namen für die VoIP-Route ein.</span><span class="sxs-lookup"><span data-stu-id="36c70-116">In the **Name** field on the **Edit Voice Route** page, type a descriptive name for the voice route.</span></span>

6.  <span data-ttu-id="36c70-117">(Optional) Geben Sie im Feld **Beschreibung** zusätzliche beschreibende Informationen zur VoIP-Route ein.</span><span class="sxs-lookup"><span data-stu-id="36c70-117">(Optional) In the **Description** field, type in additional descriptive information for the voice route.</span></span>

7.  <span data-ttu-id="36c70-118">Zur Festlegung der Muster für diese Route können Sie entweder das Tool **Muster für Vergleich erstellen** verwenden, um einen regulären Ausdruck zu generieren, oder Sie erstellen manuell einen regulären Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="36c70-118">To specify the patterns you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
      - <span data-ttu-id="36c70-p105">Geben Sie bei Verwendung des Tools **Zu suchendes Muster erstellen** zum Generieren eines regulären Ausdrucks die erforderlichen Werte wie nachfolgend beschrieben ein. Sie können zwei Arten von Mustervergleich angeben:</span><span class="sxs-lookup"><span data-stu-id="36c70-p105">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows. You can specify two types of pattern matching:</span></span>
        
          - <span data-ttu-id="36c70-121">**Anfangsziffern für Zahlen, die Sie zulassen möchten:** Geben Sie die Präfixwerte ein, die diese Route erfüllen muss (einschließlich des führenden +, falls erforderlich).</span><span class="sxs-lookup"><span data-stu-id="36c70-121">**Starting digits for numbers that you want to allow:** Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="36c70-122">Geben Sie beispielsweise **+425** ein und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="36c70-122">For example, type **+425** and then click **Add**.</span></span> <span data-ttu-id="36c70-123">Wiederholen Sie diesen Schritt für jeden Präfixwert, den Sie in der Route einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="36c70-123">Repeat this for each prefix value that you want to include in the route.</span></span>
        
          - <span data-ttu-id="36c70-124">**Ausnahmen:** Wenn Sie eine oder mehrere Ausnahmen für einen Präfixwert angeben möchten, markieren Sie das Präfix, und klicken Sie auf **Ausnahmen**.</span><span class="sxs-lookup"><span data-stu-id="36c70-124">**Exceptions:** If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="36c70-125">Geben Sie einen oder mehrere Werte für die übereinstimmenden Muster ein, die nicht für diese Route *geeignet* sein sollen.</span><span class="sxs-lookup"><span data-stu-id="36c70-125">Type in one or more values for the matching patterns that you do *not* want this route to accommodate.</span></span> <span data-ttu-id="36c70-126">Wenn Sie beispielsweise Zahlen, die mit + 425237 beginnen, von der Route ausschließen möchten, geben Sie im Feld **Ausnahmen** den Wert **+ 425237** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="36c70-126">For example, to exclude numbers starting with +425237 from the route, enter a value of **+425237** in the **Exceptions** field, and then click **OK**.</span></span>
    
      - <span data-ttu-id="36c70-127">Wenn Sie das Muster für den Vergleich manuell definieren möchten, klicken Sie im Tool **Muster für Vergleich erstellen** auf **Bearbeiten** und geben dann einen regulären .NET Framework-Ausdruck ein, um das Muster für den Vergleich von Zieltelefonnummern anzugeben, auf die die Route angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="36c70-127">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.</span></span> <span data-ttu-id="36c70-128">Informationen dazu, wie reguläre Ausdrücke geschrieben werden, finden Sie unter ".NET Framework-reguläre [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)Ausdrücke" unter.</span><span class="sxs-lookup"><span data-stu-id="36c70-128">For information about how to write regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

8.  <span data-ttu-id="36c70-p109">Wählen Sie die Option **Anrufer-ID unterdrücken**, wenn Sie nicht möchten, dass dem Anrufempfänger bei ausgehenden Anrufen die Telefon-ID angezeigt wird. Wenn Sie diese Option auswählen, müssen Sie eine **Alternative Anrufer-ID** angeben, die dem Anrufempfänger auf dem Display angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="36c70-p109">Select **Suppress caller ID** if you do not want the ID of the phone that is making the outbound call to appear to the call recipient. If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient’s caller ID display.</span></span>

9.  <span data-ttu-id="36c70-131">Klicken Sie auf **Hinzufügen**, um der VoIP-Route einen oder mehrere PSTN-Trunks (Public Switched Telephone Network Telefonfestnetz) zuzuordnen und wählen Sie aus der Liste einen Trunk aus.</span><span class="sxs-lookup"><span data-stu-id="36c70-131">To associate one or more public switched telephone network (PSTN) trunks with the voice route, click **Add**, and then select a trunk from the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="36c70-132">Wenn Ihre Bereitstellung alle Microsoft Office Communications Server 2007 R2-Vermittlungsserver umfasst, stehen diese auch in der Liste zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="36c70-132">If your deployment includes any Microsoft Office Communications Server 2007 R2 Mediation Servers, they will also be available in the list.</span></span>

    
    </div>

10. <span data-ttu-id="36c70-133">Klicken Sie auf **auswählen** , und wählen Sie einen Eintrag aus der Liste der PSTN-Nutzungsdatensätze aus, die für Ihre Enterprise-VoIP-Bereitstellung definiert wurden, um eine oder mehrere PSTN-Nutzungen der VoIP-Route zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="36c70-133">To associate one or more PSTN usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="36c70-134">Informationen zum Anzeigen der Eigenschaften der einzelnen verfügbaren PSTN-Verwendungsdaten Sätze finden Sie unter <A href="lync-server-2013-view-pstn-usage-records.md">Anzeigen von PSTN-Nutzungsdaten Sätzen in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="36c70-134">To view the properties of each of the available PSTN usage records, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="36c70-135">Informationen zum Erstellen oder Bearbeiten von PSTN-Nutzungsdaten Sätzen finden Sie unter <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013</A> oder <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="36c70-135">To create or edit PSTN usage records, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A>.</span></span>

    
    </div>

11. <span data-ttu-id="36c70-p110">Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Wenn Sie die Position eines Eintrags in der Liste ändern möchten, markieren Sie den Eintragsnamen und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.</span><span class="sxs-lookup"><span data-stu-id="36c70-p110">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="36c70-138">Im Gegensatz zu einer VoIP-Richtlinie, in der die Reihenfolge, in der die Einträge für PSTN-Nutzung aufgelistet sind, wichtig ist, ist die Reihenfolge der PSTN-Nutzungsdatensätze in einer VoIP-Route bedeutungslos.</span><span class="sxs-lookup"><span data-stu-id="36c70-138">In contrast to a voice policy where the order in which PSTN usage records are listed is important, the order of PSTN usage records in a voice route is insignificant.</span></span> <span data-ttu-id="36c70-139">Es wird jedoch empfohlen, die Liste nach Häufigkeit der Verwendung zu organisieren, beispielsweise: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="36c70-139">However, we recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="36c70-140">(Lync Server durchläuft die Liste von oben nach unten.)</span><span class="sxs-lookup"><span data-stu-id="36c70-140">(Lync Server traverses the list from the top down.)</span></span>

    
    </div>

12. <span data-ttu-id="36c70-p112">(Optional) Geben Sie im Feld **Geben Sie eine übersetzte Nummer für den Test ein** einen Wert ein und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb des Felds angezeigt.</span><span class="sxs-lookup"><span data-stu-id="36c70-p112">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**. The test results are displayed under the field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="36c70-143">Sie können eine VoIP-Route, die den Test noch nicht bestanden hat, speichern und später erneut konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="36c70-143">You can save a voice route that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="36c70-144">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-test-voice-routing.md">Testen des VoIP-Routings in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="36c70-144">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

13. <span data-ttu-id="36c70-145">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="36c70-145">Click **OK**.</span></span>

14. <span data-ttu-id="36c70-146">Klicken Sie auf der Seite **Route** auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.</span><span class="sxs-lookup"><span data-stu-id="36c70-146">On the **Route** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="36c70-147">Bei jeder Erstellung oder Änderung einer VoIP-Route müssen Sie den Befehl <STRONG>Commit für alle Elemente ausführen</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="36c70-147">Whenever you create or modify a voice route, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="36c70-148">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="36c70-148">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="36c70-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36c70-149">See Also</span></span>


[<span data-ttu-id="36c70-150">Erstellen einer VoIP-Route in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36c70-150">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="36c70-151">Anzeigen von PSTN-Nutzungsdaten Sätzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36c70-151">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="36c70-152">Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36c70-152">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="36c70-153">Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36c70-153">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="36c70-154">Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36c70-154">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="36c70-155">Testen des VoIP-Routings in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36c70-155">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

