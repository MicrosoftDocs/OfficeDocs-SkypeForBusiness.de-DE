---
title: 'Lync Server 2013: Erstellen oder Ändern eines interaktiven Workflows'
description: 'Lync Server 2013: Erstellen oder Ändern eines interaktiven Workflows.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an interactive workflow
ms:assetid: bc7bb1bc-bf6a-4636-ae93-c56fa22613fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205213(v=OCS.15)
ms:contentKeyID: 48185260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 470a073322c48c351dbfdfb24ce376731b3e7512
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546991"
---
# <a name="create-or-modify-an-interactive-workflow-in-lync-server-2013"></a><span data-ttu-id="bddd2-103">Erstellen oder Ändern eines interaktiven Workflows in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bddd2-103">Create or modify an interactive workflow in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bddd2-104">_**Letztes Änderungsstand des Themas:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="bddd2-104">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="bddd2-105">Verwenden Sie eines der folgenden Verfahren, um einen interaktiven Workflow zu erstellen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="bddd2-105">Use one of the following procedures to create or modify an interactive workflow.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bddd2-106">Sie können lync Server-Verwaltungsshell oder das Reaktionsgruppen-Konfigurations Tool verwenden, um interaktive Workflows zu erstellen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="bddd2-106">You can use Lync Server Management Shell or the Response Group Configuration Tool to create and modify interactive workflows.</span></span> <span data-ttu-id="bddd2-107">Sie können auf das Tool für die Reaktionsgruppen Konfiguration von lync Server-Systemsteuerung aus zugreifen, oder indem Sie die Webseite direkt in einem Webbrowser öffnen, indem Sie die folgende URL eingeben: <STRONG>https://</STRONG> &lt; webPoolFqdn &gt; <STRONG>/RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="bddd2-107">You can access the Response Group Configuration Tool from Lync Server Control Panel, or by opening the webpage directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="bddd2-108">So verwenden Sie das Reaktionsgruppen-Konfigurations Tool zum Erstellen oder Ändern eines interaktiven Workflows</span><span class="sxs-lookup"><span data-stu-id="bddd2-108">To use Response Group Configuration Tool to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="bddd2-109">Melden Sie sich als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="bddd2-109">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="bddd2-110">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="bddd2-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bddd2-111">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bddd2-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bddd2-112">Klicken Sie in der linken Navigationsleiste auf **Reaktionsgruppen** und dann auf **Workflow**.</span><span class="sxs-lookup"><span data-stu-id="bddd2-112">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="bddd2-113">Klicken Sie auf der Seite **Workflow** auf **Workflow erstellen oder bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="bddd2-113">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="bddd2-114">Geben Sie im Suchfeld **Dienst auswählen** den vollständigen oder Teil des Namens des **ApplicationServer** -Diensts ein, der den Workflow hostet, den Sie erstellen oder ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="bddd2-114">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or modify.</span></span> <span data-ttu-id="bddd2-115">Klicken Sie in der Dienstliste auf den gewünschten Dienst, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bddd2-115">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bddd2-116">Das Tool zum Konfigurieren von Reaktionsgruppen wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="bddd2-116">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="bddd2-117">Sie können das Tool für die Reaktionsgruppen Konfiguration auch direkt über einen Webbrowser öffnen, indem Sie die folgende URL eingeben: <STRONG>https://</STRONG> &lt; webPoolFqdn &gt; <STRONG>/RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="bddd2-117">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="bddd2-118">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="bddd2-118">Do one of the following:</span></span>
    
      - <span data-ttu-id="bddd2-119">Klicken Sie unter **neuen Workflow erstellen**neben **interaktiv**auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="bddd2-119">Under **Create a New Workflow**, next to **Interactive**, click **Create**.</span></span>
    
      - <span data-ttu-id="bddd2-120">Suchen Sie unter **Vorhandenen Workflow verwalten** nach dem Workflow, den Sie ändern möchten, und klicken Sie anschließend unter **Aktion** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="bddd2-120">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7.  <span data-ttu-id="bddd2-121">Falls Benutzer den Workflow noch nicht aufrufen sollen, müssen Sie das Kontrollkästchen **Workflow aktivieren** deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="bddd2-121">If you are not ready for users to start calling the workflow, clear the **Activate the workflow** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bddd2-p105">Wenn Sie einen verwalteten Workflow erstellen, müssen Sie <STRONG>Workflow aktivieren</STRONG> auswählen. Nachdem Sie den aktiven, verwalteten Workflow gespeichert haben, können Sie ihn ändern und deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="bddd2-p105">If you are to creating a managed workflow, you need to select <STRONG>Activate the workflow</STRONG>. After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

    
    </div>

8.  <span data-ttu-id="bddd2-124">Aktivieren Sie das Kontrollkästchen **Für Partnerverbund aktivieren**, um Partnerbenutzern Anrufe bei der Gruppe zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="bddd2-124">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="bddd2-125">Außerdem benötigen Sie eine Richtlinie für den externen Zugriff, die für den für den Verbund konfigurierten Reaktionsgruppenanwendung gilt.</span><span class="sxs-lookup"><span data-stu-id="bddd2-125">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bddd2-126">Die globale Richtlinie für den externen Zugriff gilt für die Reaktionsgruppenanwendung.</span><span class="sxs-lookup"><span data-stu-id="bddd2-126">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="bddd2-127">Sie können die globale Richtlinie für den Partnerverbund für Reaktionsgruppen konfigurieren, indem Sie lync Server-Systemsteuerung verwenden oder das Cmdlet "CsExternalAccessPolicy" verwenden, um den EnableOutsideAccess <STRONG>-</STRONG> Parameter auf "true" festzulegen.</span><span class="sxs-lookup"><span data-stu-id="bddd2-127">You can configure the global policy for response group federation by using Lync Server Control Panel or by using the <STRONG>Set-CsExternalAccessPolicy</STRONG> cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="bddd2-128">Bedenken Sie, dass globale Richtlinieneinstellungen für alle Benutzer gelten, es sei denn, sie sind einer standort- oder benutzerspezifischen Richtlinie zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="bddd2-128">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="bddd2-129">Stellen Sie daher vor dem Ändern dieser Einstellung für Reaktionsgruppen sicher, dass die Verbundeinstellung die Anforderungen Ihrer Organisation erfüllt.</span><span class="sxs-lookup"><span data-stu-id="bddd2-129">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="bddd2-130">Ausführliche Informationen dazu, wie Richtlinien auf Benutzer angewendet werden, finden Sie unter <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage External Access Policy in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="bddd2-130">For details about how policies apply to users, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span> <span data-ttu-id="bddd2-131">Ausführliche Informationen zur Verbund Einstellung finden Sie unter <STRONG>Festlegen von CsExternalAccessPolicy</STRONG> in lync Server-Verwaltungsshell Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="bddd2-131">For details about the federation setting, see <STRONG>Set-CsExternalAccessPolicy</STRONG> in Lync Server Management Shell documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bddd2-132">Benutzer, die in lync online gehostet werden, können keine Anrufe an Reaktionsgruppen abgeben, die in einer lokalen Bereitstellung gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="bddd2-132">Users who are hosted in Lync Online can’t place calls to response groups that are hosted in an on-premise deployment.</span></span> <span data-ttu-id="bddd2-133">Dies gilt sowohl für hybridbereitstellungen als auch für Fälle, in denen eine lokale Bereitstellung mit einer lync Online-Bereitstellung verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="bddd2-133">This is true in both hybrid deployments and in cases where an on-premise deployment is federated with a Lync Online deployment.</span></span>

    
    </div>

9.  <span data-ttu-id="bddd2-134">Aktivieren Sie das Kontrollkästchen **Anonymität für Agents aktivieren**, um bei Anrufen die Identität der Agents zu verbergen.</span><span class="sxs-lookup"><span data-stu-id="bddd2-134">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bddd2-135">Anonyme Anrufe können nicht mit Instant Messaging (Chat) oder Video beginnen, obwohl der Agent oder der Anrufer Chatnachrichten und Videos hinzufügen kann, nachdem der Anruf eingerichtet wurde.</span><span class="sxs-lookup"><span data-stu-id="bddd2-135">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established.</span></span> <span data-ttu-id="bddd2-136">Ein anonymer Agent kann auch Anrufe in die Warteschleife stellen, Anrufe übertragen (sowohl blinde als auch beratende Übertragungen) sowie Anrufe parken und abrufen.</span><span class="sxs-lookup"><span data-stu-id="bddd2-136">An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls.</span></span> <span data-ttu-id="bddd2-137">Anonyme Anrufe unterstützen keine Konferenzen, Anwendungsfreigaben und Desktopfreigaben, Dateiübertragungen, Whiteboards und Datenzusammenarbeit sowie die Anrufaufzeichnung.</span><span class="sxs-lookup"><span data-stu-id="bddd2-137">Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording.</span></span> <span data-ttu-id="bddd2-138">Agents, die das lync VDI-Plug-in verwenden, können eingehende Anrufe anonym empfangen, Sie können jedoch nicht anonym ausgehende Anrufe tätigen.</span><span class="sxs-lookup"><span data-stu-id="bddd2-138">Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

    
    </div>

10. <span data-ttu-id="bddd2-139">Geben Sie im Feld **Geben Sie die Adresse der Gruppe ein, die die Anrufe entgegennimmt** den primären SIP-URI (Uniform Resource Identifier) der Gruppe ein, die die Anrufe beim Workflow erhalten soll.</span><span class="sxs-lookup"><span data-stu-id="bddd2-139">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>

11. <span data-ttu-id="bddd2-140">Geben Sie im Feld **Anzeigename**den Namen ein, den Sie für den Workflow anzeigen möchten (beispielsweise Sales IVR-Reaktionsgruppe).</span><span class="sxs-lookup"><span data-stu-id="bddd2-140">In **Display name**, type the name that you want to display for the workflow (for example, Sales IVR Response Group).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bddd2-141">Schließen Sie die Zeichen " &lt; " oder " &gt; " nicht in den Anzeigenamen ein.</span><span class="sxs-lookup"><span data-stu-id="bddd2-141">Do not include the "&lt;" or "&gt;" characters in the display name.</span></span> <span data-ttu-id="bddd2-142">Die folgenden Anzeigenamen sind reserviert und dürfen nicht verwendet werden: "RGS-Anwesenheitsmonitor" oder "Ansagedienst".</span><span class="sxs-lookup"><span data-stu-id="bddd2-142">Do not use the following display names because they are reserved: RGS Presence Watcher or Announcement Service.</span></span>

    
    </div>

12. <span data-ttu-id="bddd2-143">Geben Sie unter **Telefonnummer** den Anschluss-URI für die Reaktionsgruppe ein (beispielsweise +14255550165).</span><span class="sxs-lookup"><span data-stu-id="bddd2-143">In **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="bddd2-144">Geben Sie in **Anzeigenummer** die Nummer ein, wie sie für die Reaktionsgruppe angezeigt werden soll (z. B. +1 (425) 555-0165).</span><span class="sxs-lookup"><span data-stu-id="bddd2-144">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="bddd2-145">Optional Geben Sie in **Beschreibung**eine Beschreibung für den Workflow ein, der auf der Visitenkarte im lync-Client angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="bddd2-145">(Optional) In **Description**, type a description for the workflow that you want to appear on the contact card in the Lync client.</span></span>

15. <span data-ttu-id="bddd2-146">Wählen Sie unter **Workflowtyp** die Option **Verwaltet** aus, falls dieser Workflow von einem Reaktionsgruppenmanager verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="bddd2-146">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="bddd2-147">Führen Sie die folgenden Schritte aus, um Reaktionsgruppen-Manager dem Workflow zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="bddd2-147">Do the following to assign Response Group Managers to the workflow:</span></span>
    
    1.  <span data-ttu-id="bddd2-148">Geben Sie den SIP-URI eines Managers für diesen Workflow ein, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="bddd2-148">Type the SIP URI of a manager for this workflow, and click **Add**..</span></span>
    
    2.  <span data-ttu-id="bddd2-149">Geben Sie den SIP-URI zusätzlicher Manager ein, die dem Workflow hinzugefügt werden sollen, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="bddd2-149">Type the SIP URI of additional managers to add to the workflow, and click **Add**..</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bddd2-p112">Jedem Benutzer, der als Manager einer Reaktionsgruppe bestimmt wurde, muss die Rolle CsResponseGroupManager zugewiesen sein. Falls Benutzern diese Rolle nicht zugewiesen ist, können sie keine Reaktionsgruppen verwalten.</span><span class="sxs-lookup"><span data-stu-id="bddd2-p112">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

16. <span data-ttu-id="bddd2-152">Klicken Sie unter **Schritt 2: Sprache auswählen** auf die Sprache, die für die Spracherkennung und die Text-zu-Sprache-Funktion verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="bddd2-152">Under **Step 2 Select a Language**, click the language to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="bddd2-153">Aktivieren Sie zum Konfigurieren einer Willkommensnachricht unter **Schritt 3: Willkommensnachricht konfigurieren** das Kontrollkästchen **Willkommensnachricht wiedergeben**, und führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="bddd2-153">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>
    
      - <span data-ttu-id="bddd2-154">Um die Willkommensnachricht als Text einzugeben, die für Anrufer in Sprache umgewandelt wird, klicken Sie auf **Text-zu-Sprache verwenden** und geben die Willkommensnachricht in das Textfeld ein.</span><span class="sxs-lookup"><span data-stu-id="bddd2-154">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="bddd2-p113">Verwenden Sie im eingegebenen Text keine HTML-Tags. Andernfalls wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bddd2-p113">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="bddd2-p114">Um eine aufgezeichnete WAV- oder WMA-Datei für die Willkommensnachricht zu verwenden, klicken Sie auf **Auswählen einer Aufzeichnung**. Klicken Sie auf den Link **Aufzeichnung**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Audiodatei, und klicken Sie dann auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.</span><span class="sxs-lookup"><span data-stu-id="bddd2-p114">To use a Wave or Windows Media Audio file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="bddd2-161">Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="bddd2-161">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="bddd2-162">Ausführliche Informationen zu unterstützten Dateiformaten finden Sie unter <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="bddd2-162">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

18. <span data-ttu-id="bddd2-163">Klicken Sie unter **Schritt 4: Geschäftszeiten angeben** im Feld **Ihre Zeitzone** auf die Zeitzone des Workflows.</span><span class="sxs-lookup"><span data-stu-id="bddd2-163">Under **Step 4 Specify Your Business Hours**, in the **Your time zone** box, click the time zone of the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bddd2-164">Dies ist die Zeitzone, in der sich die Anrufer und Agents des Workflows befinden.</span><span class="sxs-lookup"><span data-stu-id="bddd2-164">The time zone is the time zone where the callers and agents of the workflow reside.</span></span> <span data-ttu-id="bddd2-165">Die Angabe wird verwendet, um die Öffnungszeiten zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="bddd2-165">It is used to calculate the open and close hours.</span></span> <span data-ttu-id="bddd2-166">Wenn beispielsweise der Workflow so konfiguriert ist, dass er die Zeitzone "North American Eastern Time" verwendet und der Workflow für die Eröffnung um 7:00 Uhr geplant wird.</span><span class="sxs-lookup"><span data-stu-id="bddd2-166">For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M.</span></span> <span data-ttu-id="bddd2-167">und schließen um 11:00 Uhr werden die Öffnungs-und Schließzeiten als 7:00 Eastern Time und 11:00 Eastern Time angenommen.</span><span class="sxs-lookup"><span data-stu-id="bddd2-167">and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 11:00 Eastern Time respectively.</span></span> <span data-ttu-id="bddd2-168">(Die Zeiten müssen im 24-Stunden-Format eingegeben werden.)</span><span class="sxs-lookup"><span data-stu-id="bddd2-168">(You must enter the times in 24-hour time notation.)</span></span>

    
    </div>

19. <span data-ttu-id="bddd2-169">Sie haben folgende Möglichkeiten, um die gewünschten Geschäftszeiten anzugeben:</span><span class="sxs-lookup"><span data-stu-id="bddd2-169">Select the type of business hours schedule you want to use by doing one of the following:</span></span>
    
      - <span data-ttu-id="bddd2-170">Wenn Sie einen vordefinierten Zeitplan für die Geschäftszeiten verwenden möchten, klicken Sie auf **Verwenden eines vordefinierten Zeitplans**, und wählen Sie den gewünschten Zeitplan in der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="bddd2-170">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="bddd2-171">Sie müssen mindestens einen vordefinierten Zeitplan erstellt haben, um diese Option auswählen zu können.</span><span class="sxs-lookup"><span data-stu-id="bddd2-171">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="bddd2-172">Sie erstellen vordefinierte Zeitpläne mit dem Cmdlet <STRONG>New-CSRgsHoursOfBusiness</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="bddd2-172">You define preset schedules by using the <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet.</span></span> <span data-ttu-id="bddd2-173">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-optional-define-response-group-business-hours.md">(optional) definieren von Geschäftszeiten für Reaktionsgruppen in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="bddd2-173">For details, see <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</A>.</span></span> <span data-ttu-id="bddd2-174">Wenn Sie einen vordefinierten Zeitplan verwenden, werden die Werte für <STRONG>Tag</STRONG>, <STRONG>Öffnen</STRONG> und <STRONG>Schließen</STRONG>, an denen die Reaktionsgruppe verfügbar ist, automatisch eingetragen.</span><span class="sxs-lookup"><span data-stu-id="bddd2-174">When you select a preset schedule, <STRONG>Day</STRONG>, <STRONG>Open</STRONG>, and <STRONG>Close</STRONG> are automatically filled with the days and hours that the response group is available.</span></span>

        
        </div>
    
      - <span data-ttu-id="bddd2-175">Klicken Sie auf **Verwenden eines benutzerdefinierten Zeitplans**, um einen benutzerdefinierten Zeitplan zu erstellen, der nur für diesen Workflow gilt.</span><span class="sxs-lookup"><span data-stu-id="bddd2-175">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="bddd2-176">Wenn Sie einen benutzerdefinierten Zeitplan für diesen Workflow erstellen, aktivieren Sie die Kontrollkästchen für die Wochentage, an denen die Reaktionsgruppe verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="bddd2-176">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="bddd2-177">Beim Erstellen eines benutzerdefinierten Zeitplans geben Sie über die Werte für **Öffnen** und **Schließen** den Zeitraum ein, in dem die Reaktionsgruppe verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="bddd2-177">If you are creating a custom schedule, type the **Open** and **Close** hours when the response group available.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bddd2-p118">Die Werte für <STRONG>Öffnen</STRONG> und <STRONG>Schließen</STRONG> müssen im 24-Stunden-Format angegeben werden. Wenn Ihr Büro z. B. von 9 Uhr bis 17 Uhr geöffnet und mittags geschlossen ist, können Sie die Geschäftszeiten als <STRONG>Öffnen</STRONG> 9:00, <STRONG>Schließen</STRONG> 12:00, <STRONG>Öffnen</STRONG> 13:00 und <STRONG>Schließen</STRONG> 17:00 angeben.</span><span class="sxs-lookup"><span data-stu-id="bddd2-p118">The <STRONG>Open</STRONG> and <STRONG>Close</STRONG> hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as <STRONG>Open</STRONG> 9:00, <STRONG>Close</STRONG> 12:00, <STRONG>Open</STRONG> 13:00, and <STRONG>Close</STRONG> 17:00.</span></span>

    
    </div>

22. <span data-ttu-id="bddd2-180">Wenn Sie eine Nachricht wiedergeben möchten, wenn das Büro geschlossen ist, aktivieren Sie das Kontrollkästchen **Wiedergabe einer Nachricht, wenn sich die Reaktionsgruppe außerhalb der Geschäftszeiten befindet**, und geben Sie die Nachricht ein, indem Sie eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="bddd2-180">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="bddd2-181">Um die Nachricht als Text einzugeben, die für Anrufer in Sprache umgewandelt wird, klicken Sie auf **Text-zu-Sprache verwenden** und geben die Nachricht in das Textfeld ein.</span><span class="sxs-lookup"><span data-stu-id="bddd2-181">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="bddd2-p119">Verwenden Sie im eingegebenen Text keine HTML-Tags. Andernfalls wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bddd2-p119">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="bddd2-p120">Um eine aufgezeichnete Audiodatei als Nachricht zu verwenden, klicken Sie auf **Auswählen einer Aufzeichnung**. Klicken Sie auf den Link **Aufzeichnung**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Datei, und klicken Sie auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.</span><span class="sxs-lookup"><span data-stu-id="bddd2-p120">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="bddd2-188">Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="bddd2-188">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="bddd2-189">Ausführliche Informationen zu unterstützten Dateiformaten finden Sie unter <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="bddd2-189">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

23. <span data-ttu-id="bddd2-190">Geben Sie an, wie nach Wiedergabe der Nachricht verfahren werden soll (sofern eine Nachricht konfiguriert wurde):</span><span class="sxs-lookup"><span data-stu-id="bddd2-190">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="bddd2-191">Klicken Sie auf **Verbindung trennen**, um die Verbindung zu trennen.</span><span class="sxs-lookup"><span data-stu-id="bddd2-191">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="bddd2-192">Um den Anruf an ein Voicemailsystem weiterzuleiten, klicken Sie auf **An Voicemail weiterleiten** und geben die Voicemailadresse ein.</span><span class="sxs-lookup"><span data-stu-id="bddd2-192">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="bddd2-193">Das Format für die Voicemail-Adresse lautet \<username\> @ \<domainname\> (beispielsweise Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="bddd2-193">The format for the voice mail address is \<username\>@\<domainname\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="bddd2-194">Um den Anruf an einen anderen Benutzer weiterzuleiten, klicken Sie auf **An SIP-URI weiterleiten** und geben die Adresse eines Benutzers ein.</span><span class="sxs-lookup"><span data-stu-id="bddd2-194">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="bddd2-195">Das Format für die Benutzeradresse lautet \<username\> @ \<domainname\> .</span><span class="sxs-lookup"><span data-stu-id="bddd2-195">The format for the user address is \<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="bddd2-196">Um den Anruf an eine andere Telefonnummer weiterzuleiten, klicken Sie auf **An Telefonnummer weiterleiten** und geben die Telefonnummer ein.</span><span class="sxs-lookup"><span data-stu-id="bddd2-196">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="bddd2-197">Das Format für die Telefonnummer lautet \<number\> @ \<domainname\> (beispielsweise + 14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="bddd2-197">The format for the telephone number is \<number\>@\<domainname\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="bddd2-198">Der Domänenname wird verwendet, um den Anrufer an das richtige Ziel weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="bddd2-198">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="bddd2-199">Aktivieren Sie unter **Schritt 5: Feiertage angeben** die Kontrollkästchen für einen oder mehrere Feiertagssätze, mit denen die Tage definiert werden, an denen die Reaktionsgruppe aufgrund eines Feiertags nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="bddd2-199">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bddd2-200">Sie müssen die für Sie geltenden Feiertage und Feiertagssätze definieren, bevor Sie den Workflow konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="bddd2-200">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="bddd2-201">Verwenden Sie zum Definieren von Feiertagen und Feiertagssätzen die Cmdlets <STRONG>New-CsRgsHoliday</STRONG> und <STRONG>New-CsRgsHolidaySet</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="bddd2-201">Use the <STRONG>New-CsRgsHoliday</STRONG> and <STRONG>New-CsRgsHolidaySet</STRONG> cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="bddd2-202">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(optional) definieren von Feiertagssätzen für Reaktionsgruppen in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="bddd2-202">For details, see <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</A>.</span></span>

    
    </div>

25. <span data-ttu-id="bddd2-203">Wenn Sie an Feiertagen eine Nachricht wiedergeben möchten, aktivieren Sie das Kontrollkästchen **Wiedergabe einer Nachricht an Feiertagen**, und geben Sie die Nachricht an, indem Sie eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="bddd2-203">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="bddd2-204">Um die Nachricht als Text einzugeben, die für Anrufer in Sprache umgewandelt wird, klicken Sie auf **Text-zu-Sprache verwenden** und geben die Nachricht in das Textfeld ein.</span><span class="sxs-lookup"><span data-stu-id="bddd2-204">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="bddd2-p126">Verwenden Sie im eingegebenen Text keine HTML-Tags. Andernfalls wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bddd2-p126">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="bddd2-p127">Um eine aufgezeichnete Audiodatei als Nachricht zu verwenden, klicken Sie auf **Auswählen einer Aufzeichnung**. Klicken Sie auf den Link **Aufzeichnung**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Datei, und klicken Sie auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.</span><span class="sxs-lookup"><span data-stu-id="bddd2-p127">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="bddd2-211">Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="bddd2-211">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="bddd2-212">Ausführliche Informationen zu unterstützten Audiodatei Formaten finden Sie unter <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="bddd2-212">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

26. <span data-ttu-id="bddd2-213">Geben Sie an, wie nach Wiedergabe der Nachricht verfahren werden soll (sofern eine Nachricht konfiguriert wurde):</span><span class="sxs-lookup"><span data-stu-id="bddd2-213">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="bddd2-214">Klicken Sie auf **Verbindung trennen**, um die Verbindung zu trennen.</span><span class="sxs-lookup"><span data-stu-id="bddd2-214">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="bddd2-215">Um den Anruf an ein Voicemailsystem weiterzuleiten, klicken Sie auf **An Voicemail weiterleiten** und geben die Voicemailadresse ein.</span><span class="sxs-lookup"><span data-stu-id="bddd2-215">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="bddd2-216">Das Format für die Voicemail-Adresse lautet \<username\> @ \<domainname\> (beispielsweise Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="bddd2-216">The format for the voice mail address is \<username\>@\<domainname\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="bddd2-217">Um den Anruf an einen anderen Benutzer weiterzuleiten, klicken Sie auf **An SIP-URI weiterleiten** und geben die Adresse eines Benutzers ein.</span><span class="sxs-lookup"><span data-stu-id="bddd2-217">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="bddd2-218">Das Format für die Benutzeradresse lautet \<username\> @ \<domainname\> .</span><span class="sxs-lookup"><span data-stu-id="bddd2-218">The format for the user address is \<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="bddd2-219">Um den Anruf an eine andere Telefonnummer weiterzuleiten, klicken Sie auf **An Telefonnummer weiterleiten** und geben die Telefonnummer ein.</span><span class="sxs-lookup"><span data-stu-id="bddd2-219">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="bddd2-220">Das Format für die Telefonnummer lautet \<number\> @ \<domainname\> (beispielsweise + 14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="bddd2-220">The format for the telephone number is \<number\>@\<domainname\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="bddd2-221">Der Domänenname wird verwendet, um den Anrufer an das richtige Ziel weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="bddd2-221">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="bddd2-222">Wählen Sie unter **Schritt 6: Wartemusik konfigurieren** aus, was Anrufer beim Warten auf einen Agent hören sollen, indem Sie eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="bddd2-222">Under **Step 6 Configure Music on Hold**, choose what you want callers to listen to while waiting for an agent by doing one of the following:</span></span>
    
      - <span data-ttu-id="bddd2-223">Klicken Sie auf **Standard verwenden**, um die Standardwartemusik zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="bddd2-223">To use the default music on-hold recording, click **Use default**.</span></span>
    
      - <span data-ttu-id="bddd2-p132">Klicken Sie auf **Auswählen einer Musikdatei**, um eine aufgezeichnete Audiodatei als Wartemusik zu verwenden. Klicken Sie auf den Link **Musikdatei**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Datei, und klicken Sie auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.</span><span class="sxs-lookup"><span data-stu-id="bddd2-p132">To use an audio file recording for the on-hold music, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="bddd2-228">Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="bddd2-228">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="bddd2-229">Ausführliche Informationen zu unterstützten Dateiformaten finden Sie unter <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="bddd2-229">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

28. <span data-ttu-id="bddd2-230">Geben Sie in **Schritt 7: Interaktive Sprachantwort (IVR) konfigurieren** unter **Der Benutzer hört den folgenden Text bzw. die folgende aufgezeichnete Nachricht** die Frage ein, die dem Anrufer gestellt wird. Führen Sie hierzu die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="bddd2-230">Under **Step 7 Configure Interactive Voice Response**, under the **The user will hear the following text or recorded message** heading, specify the question to ask callers as follows:</span></span>
    
      - <span data-ttu-id="bddd2-231">Um die Frage im Textformat einzugeben, klicken Sie auf **Text-zu-Sprache verwenden** und geben die Frage in das Textfeld ein.</span><span class="sxs-lookup"><span data-stu-id="bddd2-231">To enter the question in text format, click **Use text-to-speech**, and type the question in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="bddd2-p134">Verwenden Sie im eingegebenen Text keine HTML-Tags. Andernfalls wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bddd2-p134">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="bddd2-234">Das Symbol "#" wird vom Text-zu-Sprache-Modul als das Wort "Nummer" übersetzt.</span><span class="sxs-lookup"><span data-stu-id="bddd2-234">The "#" symbol is translated by the text-to-speech engine as the word "number".</span></span> <span data-ttu-id="bddd2-235">Wenn Sie auf die Taste # verweisen möchten, sollten Sie bei der Eingabe anstelle des Symbols den Tastennamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="bddd2-235">If you need to refer to the # key, you should use the key name, rather than the symbol, in your prompt.</span></span> <span data-ttu-id="bddd2-236">Wenn Sie beispielsweise "mit Vertrieb sprechen möchten, drücken Sie die Taste Pound".</span><span class="sxs-lookup"><span data-stu-id="bddd2-236">For example, "To talk to sales, press the pound key."</span></span>

        
        </div>
    
      - <span data-ttu-id="bddd2-p136">Um eine aufgezeichnete Audiodatei mit der Frage zu verwenden, klicken Sie auf **Auswählen einer Aufzeichnung** und dann auf den Link **Aufzeichnung**, um die Datei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Audiodatei, und klicken Sie auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden, und geben Sie dann optional die Frage in das Textfeld ein (auf diese Weise kann die Frage und die Antwort des Anrufers an den zuständigen Agent weitergeleitet werden).</span><span class="sxs-lookup"><span data-stu-id="bddd2-p136">To use a prerecorded audio file that contains the question, click **Select a recording**, and then click the **a recording** link to upload the file. In the new browser window, click **Browse**, select the audio file, and then click **Open**. Click **Upload** to load the file, and then optionally you can type the question in the text box (this enables the question, and the caller’s response, to be forwarded to the responding agent).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="bddd2-240">Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="bddd2-240">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="bddd2-241">Ausführliche Informationen zu unterstützten Dateiformaten finden Sie unter <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="bddd2-241">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

29. <span data-ttu-id="bddd2-242">Geben Sie unter **Antwort 1** wie folgt die erste mögliche Antwort auf die Frage ein:</span><span class="sxs-lookup"><span data-stu-id="bddd2-242">Under **Response 1**, specify the first possible answer to the question by doing the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bddd2-p138">Verwenden Sie in Sprachantworten keine Anführungszeichen ("). Bei Verwendung von Anführungszeichen funktioniert die interaktive Sprachantwort nicht ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="bddd2-p138">Do not use quotation marks (") in any voice responses. Quotation marks cause the IVR to fail.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bddd2-245">Sie können auswählen, ob Anrufer per Sprache, Tasteneingabe oder beidem antworten können.</span><span class="sxs-lookup"><span data-stu-id="bddd2-245">You can choose to allow callers to answer using speech, alphanumeric keypad input, or both.</span></span>

    
    </div>
    
      - <span data-ttu-id="bddd2-246">Wenn Sie zulassen möchten, dass Anrufer per Sprache antworten, geben Sie die Antwort in das Feld **Geben Sie eine Sprachantwort ein** ein.</span><span class="sxs-lookup"><span data-stu-id="bddd2-246">If you want to allow the caller to respond using speech, enter the answer in **Enter a voice response**.</span></span>
    
      - <span data-ttu-id="bddd2-247">Wenn Sie zulassen möchten, dass Anrufer per Tasteneingabe antworten, klicken Sie im Feld **Ziffer** auf die entsprechende Ziffer.</span><span class="sxs-lookup"><span data-stu-id="bddd2-247">If you want to allow the caller to respond by pressing a key on the keypad, in **Digit**, click the keypad digit.</span></span>

30. <span data-ttu-id="bddd2-248">Geben Sie wie folgt an, ob der Anrufer an eine Warteschleife weitergeleitet wird, oder ob eine weitere Frage gestellt werden soll:</span><span class="sxs-lookup"><span data-stu-id="bddd2-248">Specify whether to route the caller to a queue, or to ask another question as follows:</span></span>
    
      - <span data-ttu-id="bddd2-249">Um den Anrufer an eine Warteschleife weiterzuleiten, klicken Sie auf **An eine Warteschleife senden**, und klicken Sie unter **Warteschleife auswählen** auf die Warteschleife, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="bddd2-249">To route the caller to a queue, click **Send to a queue**, and in **Select a queue**, click the queue that you want to use.</span></span>
    
      - <span data-ttu-id="bddd2-p139">Wenn eine weitere Frage gestellt werden soll, klicken Sie auf **Eine weitere Frage stellen**, klicken Sie dann auf **Text-zu-Sprache verwenden**, und geben Sie die Frage ein, oder klicken Sie auf **Auswählen einer Aufzeichnung**. Verwenden Sie die Einstellungen in diesem Abschnitt, um bis zu vier mögliche Antworten auf die zusätzliche Frage sowie die Warteschleife für jede Antwort anzugeben. Um eine dritte oder vierte mögliche Antwort anzugeben, aktivieren Sie das Kontrollkästchen **Antwort 3** oder das Kontrollkästchen **Antwort 4**.</span><span class="sxs-lookup"><span data-stu-id="bddd2-p139">To ask another question, click **Ask another question**, and then click **Use text-to-speech** and type the question, or click **Select a recording**. Use the response groupings in this section to specify up to four possible responses to the additional question and the queue to use for each response. To specify a third or fourth possible response, click the **Response 3** check box or the **Response 4** check box.</span></span>

31. <span data-ttu-id="bddd2-253">Geben Sie bis zu drei weitere mögliche Antworten auf die ursprüngliche Frage ein, indem Sie die Schritte 28 und 29 wiederholen, um mögliche Antworten und die Aktion für jede Antwort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="bddd2-253">Specify up to three more possible answers to the original question by repeating steps 28 and 29 to specify the possible responses and the action to take for each response.</span></span> <span data-ttu-id="bddd2-254">Um eine dritte oder vierte mögliche Antwort anzugeben, aktivieren Sie das Kontrollkästchen **Antwort 3** oder das Kontrollkästchen **Antwort 4** .</span><span class="sxs-lookup"><span data-stu-id="bddd2-254">To specify a third or fourth possible answer, click the **Response 3** check box or the **Response 4** check box.</span></span>

32. <span data-ttu-id="bddd2-255">Klicken Sie auf **Bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="bddd2-255">Click **Deploy**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="bddd2-256">So verwenden Sie Windows PowerShell zum Erstellen oder Ändern eines interaktiven Workflows</span><span class="sxs-lookup"><span data-stu-id="bddd2-256">To use Windows PowerShell to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="bddd2-257">Melden Sie sich als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="bddd2-257">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="bddd2-258">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="bddd2-258">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="bddd2-259">Dienstnamen für den Reaktionsgruppendienst abrufen und diesen einer Variable zuweisen.</span><span class="sxs-lookup"><span data-stu-id="bddd2-259">Retrieve the service name for the Response Group service and assign it to a variable.</span></span> <span data-ttu-id="bddd2-260">Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="bddd2-260">At the command line, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

4.  <span data-ttu-id="bddd2-261">Für einen interaktiven Workflow sind mindestens zwei Warteschlangen und zwei oder mehr Agentengruppen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bddd2-261">An interactive workflow requires two or more queues and two or more agent groups.</span></span> <span data-ttu-id="bddd2-262">Erstellen Sie zuerst die Agentengruppen.</span><span class="sxs-lookup"><span data-stu-id="bddd2-262">First, create the agent groups.</span></span> <span data-ttu-id="bddd2-263">Ausführen</span><span class="sxs-lookup"><span data-stu-id="bddd2-263">Run:</span></span>
    
        $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
        $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]

5.  <span data-ttu-id="bddd2-264">Erstellen Sie die Warteschlangen.</span><span class="sxs-lookup"><span data-stu-id="bddd2-264">Create the queues.</span></span> <span data-ttu-id="bddd2-265">Ausführen</span><span class="sxs-lookup"><span data-stu-id="bddd2-265">Run:</span></span>
    
        $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
        $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)

6.  <span data-ttu-id="bddd2-266">Erstellen Sie die erste Reaktionsgruppen-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="bddd2-266">Create the first response group prompt.</span></span> <span data-ttu-id="bddd2-267">Ausführen</span><span class="sxs-lookup"><span data-stu-id="bddd2-267">Run:</span></span>
    
        $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."

7.  <span data-ttu-id="bddd2-268">Erstellen Sie dann die Aktion, die nach der Eingabeaufforderung ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="bddd2-268">Then create the action to be performed after the prompt.</span></span> <span data-ttu-id="bddd2-269">Ausführen</span><span class="sxs-lookup"><span data-stu-id="bddd2-269">Run:</span></span>
    
        $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity

8.  <span data-ttu-id="bddd2-270">Erstellen Sie die erste Antwortgruppen Antwort.</span><span class="sxs-lookup"><span data-stu-id="bddd2-270">Create the first response group answer.</span></span> <span data-ttu-id="bddd2-271">Ausführen</span><span class="sxs-lookup"><span data-stu-id="bddd2-271">Run:</span></span>
    
        $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]

9.  <span data-ttu-id="bddd2-272">Erstellen Sie nun die zweite Eingabeaufforderung, anrufaktion und Antwort.</span><span class="sxs-lookup"><span data-stu-id="bddd2-272">Now create the second prompt, call action, and answer.</span></span> <span data-ttu-id="bddd2-273">Erstellen Sie zuerst die Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="bddd2-273">First create the prompt.</span></span> <span data-ttu-id="bddd2-274">Ausführen</span><span class="sxs-lookup"><span data-stu-id="bddd2-274">Run:</span></span>
    
        $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."

10. <span data-ttu-id="bddd2-275">Erstellen Sie die zweite anrufaktion.</span><span class="sxs-lookup"><span data-stu-id="bddd2-275">Create the second call action.</span></span> <span data-ttu-id="bddd2-276">Ausführen</span><span class="sxs-lookup"><span data-stu-id="bddd2-276">Run:</span></span>
    
        $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity

11. <span data-ttu-id="bddd2-277">Erstellen Sie die zweite Antwortgruppen Antwort.</span><span class="sxs-lookup"><span data-stu-id="bddd2-277">Create the second response group answer.</span></span> <span data-ttu-id="bddd2-278">Ausführen</span><span class="sxs-lookup"><span data-stu-id="bddd2-278">Run:</span></span>
    
        $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]

12. <span data-ttu-id="bddd2-279">Erstellen Sie die Eingabeaufforderung auf oberster Ebene.</span><span class="sxs-lookup"><span data-stu-id="bddd2-279">Create the top-level prompt.</span></span> <span data-ttu-id="bddd2-280">Ausführen</span><span class="sxs-lookup"><span data-stu-id="bddd2-280">Run:</span></span>
    
        $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."

13. <span data-ttu-id="bddd2-281">Erstellen Sie die Frage auf oberster Ebene.</span><span class="sxs-lookup"><span data-stu-id="bddd2-281">Create the top-level question.</span></span> <span data-ttu-id="bddd2-282">Ausführen</span><span class="sxs-lookup"><span data-stu-id="bddd2-282">Run:</span></span>
    
        $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]

14. <span data-ttu-id="bddd2-283">Erstellen Sie nun den Workflow.</span><span class="sxs-lookup"><span data-stu-id="bddd2-283">Now create the workflow.</span></span> <span data-ttu-id="bddd2-284">Ausführen</span><span class="sxs-lookup"><span data-stu-id="bddd2-284">Run:</span></span>
    
        $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
        $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bddd2-285">Allen Benutzern, die als Manager einer Reaktionsgruppe festgelegt wurden, muss die Rolle "th Rolle csresponsegroupmanager" zugewiesen sein.</span><span class="sxs-lookup"><span data-stu-id="bddd2-285">All users who have been designated as manager of a response group must be assigned th CsResponseGroupManager role.</span></span> <span data-ttu-id="bddd2-286">Falls Benutzern diese Rolle nicht zugewiesen ist, können sie keine Reaktionsgruppen verwalten.</span><span class="sxs-lookup"><span data-stu-id="bddd2-286">If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

