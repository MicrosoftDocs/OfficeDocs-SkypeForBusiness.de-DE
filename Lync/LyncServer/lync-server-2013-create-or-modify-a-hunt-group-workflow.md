---
title: 'Lync Server 2013: Erstellen oder Ändern eines Sammelanschluss-Workflows'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a hunt group workflow
ms:assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205321(v=OCS.15)
ms:contentKeyID: 48185596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f56187645a48b4e2cdaebb8ce9091abcfadc065b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-hunt-group-workflow-in-lync-server-2013"></a><span data-ttu-id="a51ef-102">Erstellen oder Ändern eines Sammelanschluss-Workflows in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a51ef-102">Create or modify a hunt group workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a51ef-103">_**Letztes Änderungsstand des Themas:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="a51ef-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="a51ef-104">Verwenden Sie eines der folgenden Verfahren, um einen Workflow für Sammelanschlüsse zu erstellen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a51ef-104">Use one of the following procedures to create or modify a hunt group workflow.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a51ef-105">Sie können lync Server-Verwaltungsshell oder das Reaktionsgruppen-Konfigurations Tool zum Erstellen und Ändern von Sammelanschluss-Workflows verwenden.</span><span class="sxs-lookup"><span data-stu-id="a51ef-105">You can use Lync Server Management Shell or the Response Group Configuration Tool to create and modify hunt group workflows.</span></span> <span data-ttu-id="a51ef-106">Sie können auf das Tool für die Reaktionsgruppen Konfiguration von lync Server-Systemsteuerung aus zugreifen, oder indem Sie die Webseite direkt in einem Webbrowser öffnen, indem Sie die folgende URL eingeben: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a51ef-106">You can access the Response Group Configuration Tool from Lync Server Control Panel, or by opening the webpage directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="a51ef-107">So verwenden Sie das Reaktionsgruppen-Konfigurations Tool zum Erstellen oder Ändern eines Sammelanschluss-Workflows</span><span class="sxs-lookup"><span data-stu-id="a51ef-107">To use Response Group Configuration Tool to create or modify a hunt group workflow</span></span>

1.  <span data-ttu-id="a51ef-108">Melden Sie sich als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a51ef-108">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="a51ef-109">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a51ef-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a51ef-110">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a51ef-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a51ef-111">Klicken Sie in der linken Navigationsleiste auf **Reaktionsgruppen** und dann auf **Workflow**.</span><span class="sxs-lookup"><span data-stu-id="a51ef-111">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="a51ef-112">Klicken Sie auf der Seite **Workflow** auf **Workflow erstellen oder bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="a51ef-112">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="a51ef-113">Geben Sie im Suchfeld **Dienst auswählen** einen Teil oder den vollständigen Namen des **ApplicationServer**-Diensts ein, von dem der Workflow gehostet wird, den Sie erstellen oder ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="a51ef-113">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or change.</span></span> <span data-ttu-id="a51ef-114">Klicken Sie in der Dienstliste auf den gewünschten Dienst, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a51ef-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a51ef-115">Das Tool zum Konfigurieren von Reaktionsgruppen wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a51ef-115">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="a51ef-116">Sie können das Tool für die Reaktionsgruppen Konfiguration auch direkt über einen Webbrowser öffnen, indem Sie die folgende URL eingeben: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a51ef-116">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="a51ef-117">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="a51ef-117">Do one of the following:</span></span>
    
      - <span data-ttu-id="a51ef-118">Klicken Sie unter **neuen Workflow erstellen**neben **"Sammelvorgang" auf Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="a51ef-118">Under **Create a New Workflow**, next to **Hunt Group, click Create**.</span></span>
    
      - <span data-ttu-id="a51ef-119">Suchen Sie unter **Vorhandenen Workflow verwalten** nach dem Workflow, den Sie ändern möchten, und klicken Sie anschließend unter **Aktion** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="a51ef-119">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7.  <span data-ttu-id="a51ef-120">Falls Benutzer den Workflow bereits verwenden können, aktivieren Sie das Kontrollkästchen **Workflow aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="a51ef-120">If you are ready for users to start calling the workflow, select **Activate the workflow**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a51ef-p105">Wenn Sie einen verwalteten Workflow erstellen, müssen Sie <STRONG>Workflow aktivieren</STRONG> auswählen. Nachdem Sie den aktiven, verwalteten Workflow gespeichert haben, können Sie ihn ändern und deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a51ef-p105">If you are to creating a managed workflow, you need to select <STRONG>Activate the workflow</STRONG>. After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

    
    </div>

8.  <span data-ttu-id="a51ef-123">Aktivieren Sie das Kontrollkästchen **Für Partnerverbund aktivieren**, um Partnerbenutzern Anrufe bei der Gruppe zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a51ef-123">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="a51ef-124">Außerdem benötigen Sie eine Richtlinie für den externen Zugriff, die für den für den Verbund konfigurierten Reaktionsgruppenanwendung gilt.</span><span class="sxs-lookup"><span data-stu-id="a51ef-124">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a51ef-125">Die globale Richtlinie für den externen Zugriff gilt für die Reaktionsgruppenanwendung.</span><span class="sxs-lookup"><span data-stu-id="a51ef-125">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="a51ef-126">Sie können die globale Richtlinie für den Partnerverbund für Reaktionsgruppen konfigurieren, indem Sie lync Server-Systemsteuerung verwenden oder das Cmdlet "CsExternalAccessPolicy" verwenden, um den EnableOutsideAccess <STRONG>-</STRONG> Parameter auf "true" festzulegen.</span><span class="sxs-lookup"><span data-stu-id="a51ef-126">You can configure the global policy for response group federation by using Lync Server Control Panel or by using the <STRONG>Set-CsExternalAccessPolicy</STRONG> cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="a51ef-127">Bedenken Sie, dass globale Richtlinieneinstellungen für alle Benutzer gelten, es sei denn, sie sind einer standort- oder benutzerspezifischen Richtlinie zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="a51ef-127">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="a51ef-128">Stellen Sie daher vor dem Ändern dieser Einstellung für Reaktionsgruppen sicher, dass die Verbundeinstellung die Anforderungen Ihrer Organisation erfüllt.</span><span class="sxs-lookup"><span data-stu-id="a51ef-128">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="a51ef-129">Ausführliche Informationen dazu, wie Richtlinien auf Benutzer angewendet werden, finden Sie unter <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage External Access Policy in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a51ef-129">For details about how policies apply to users, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span> <span data-ttu-id="a51ef-130">Ausführliche Informationen zur Partnerverbund Einstellung finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">Sets-CsExternalAccessPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="a51ef-130">For details about the federation setting, see <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">Set-CsExternalAccessPolicy</A>.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a51ef-131">Benutzer, die in lync online gehostet werden, können keine Anrufe an Reaktionsgruppen abgeben, die in einer lokalen Bereitstellung gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="a51ef-131">Users who are hosted in Lync Online can’t place calls to response groups that are hosted in an on-premise deployment.</span></span> <span data-ttu-id="a51ef-132">Dies gilt sowohl für hybridbereitstellungen als auch für Fälle, in denen eine lokale Bereitstellung mit einer lync Online-Bereitstellung verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="a51ef-132">This is true in both hybrid deployments and in cases where an on-premise deployment is federated with a Lync Online deployment.</span></span>

    
    </div>

9.  <span data-ttu-id="a51ef-133">Aktivieren Sie das Kontrollkästchen **Anonymität für Agents aktivieren**, um bei Anrufen die Identität der Agents zu verbergen.</span><span class="sxs-lookup"><span data-stu-id="a51ef-133">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a51ef-134">Anonyme Anrufe können nicht mit Instant Messaging (Chat) oder Video beginnen, obwohl der Agent oder der Anrufer Chatnachrichten und Videos hinzufügen kann, nachdem der Anruf eingerichtet wurde.</span><span class="sxs-lookup"><span data-stu-id="a51ef-134">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established.</span></span> <span data-ttu-id="a51ef-135">Ein anonymer Agent kann auch Anrufe in die Warteschleife stellen, Anrufe übertragen (sowohl blinde als auch beratende Übertragungen) sowie Anrufe parken und abrufen.</span><span class="sxs-lookup"><span data-stu-id="a51ef-135">An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls.</span></span> <span data-ttu-id="a51ef-136">Anonyme Anrufe unterstützen keine Konferenzen, Anwendungsfreigaben und Desktopfreigaben, Dateiübertragungen, Whiteboards und Datenzusammenarbeit sowie die Anrufaufzeichnung.</span><span class="sxs-lookup"><span data-stu-id="a51ef-136">Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording.</span></span> <span data-ttu-id="a51ef-137">Agents, die das lync VDI-Plug-in verwenden, können eingehende Anrufe anonym empfangen, Sie können jedoch nicht anonym ausgehende Anrufe tätigen.</span><span class="sxs-lookup"><span data-stu-id="a51ef-137">Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

    
    </div>

10. <span data-ttu-id="a51ef-138">Geben Sie im Feld **Geben Sie die Adresse der Gruppe ein, die die Anrufe entgegennimmt** den primären SIP-URI (Uniform Resource Identifier) der Gruppe ein, die die Anrufe beim Workflow erhalten soll.</span><span class="sxs-lookup"><span data-stu-id="a51ef-138">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a51ef-139">Über den primären URI für einen Workflow wird der Workflow identifiziert.</span><span class="sxs-lookup"><span data-stu-id="a51ef-139">The primary URI for a workflow is how the workflow is identified and referenced.</span></span> <span data-ttu-id="a51ef-140">Der SIP-URI, den Sie eingeben, wird in Active Directory-Domänendienste als Kontaktobjekt erstellt.</span><span class="sxs-lookup"><span data-stu-id="a51ef-140">The SIP URI that you enter is created as a contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="a51ef-141">Um den URI zu erstellen, muss das Objekt in Active Directory eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="a51ef-141">To create the URI, the object must be unique in Active Directory.</span></span>

    
    </div>

11. <span data-ttu-id="a51ef-142">Geben Sie unter **Anzeigename**den Namen ein, den Sie für den Workflow anzeigen möchten (beispielsweise Vertriebs Reaktionsgruppe).</span><span class="sxs-lookup"><span data-stu-id="a51ef-142">In **Display name**, type the name that you want to display for the workflow (for example, Sales Response Group).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a51ef-143">Schließen Sie die Zeichen "&lt;" oder "&gt;" nicht in den Anzeigenamen ein.</span><span class="sxs-lookup"><span data-stu-id="a51ef-143">Do not include the "&lt;" or "&gt;" characters in the display name.</span></span> <span data-ttu-id="a51ef-144">Die folgenden Anzeigenamen sind reserviert und dürfen nicht verwendet werden: <STRONG>RGS-Anwesenheitsmonitor</STRONG> oder <STRONG>Ankündigungsdienst</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a51ef-144">Do not use the following display names because they are reserved: <STRONG>RGS Presence Watcher</STRONG> or <STRONG>Announcement Service</STRONG>.</span></span>

    
    </div>

12. <span data-ttu-id="a51ef-145">Geben Sie unter **Telefonnummer** den Anschluss-URI für die Reaktionsgruppe ein (z. B. +14255550165).</span><span class="sxs-lookup"><span data-stu-id="a51ef-145">Under **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="a51ef-146">Geben Sie in **Anzeigenummer** die Nummer ein, wie sie für die Reaktionsgruppe angezeigt werden soll (z. B. +1 (425) 555-0165).</span><span class="sxs-lookup"><span data-stu-id="a51ef-146">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="a51ef-147">Optional Geben Sie in **Beschreibung**eine Beschreibung für den Workflow ein, so wie er auf der Visitenkarte in lync-Client angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a51ef-147">(Optional) In **Description**, type a description for the workflow as you want it to appear on the contact card in Lync client.</span></span>

15. <span data-ttu-id="a51ef-148">Wählen Sie unter **Workflowtyp** die Option **Verwaltet** aus, falls dieser Workflow von einem Reaktionsgruppenmanager verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="a51ef-148">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="a51ef-149">Führen Sie die folgenden Schritte aus, um Reaktionsgruppen-Manager dem Workflow zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="a51ef-149">Do the following to assign Response Group Managers to the workflow:</span></span>
    
    1.  <span data-ttu-id="a51ef-150">Geben Sie den SIP-URI eines Managers für diesen Workflow ein, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a51ef-150">Type the SIP URI of a manager for this workflow, and click **Add**.</span></span>
    
    2.  <span data-ttu-id="a51ef-151">Geben Sie den SIP-URI zusätzlicher Manager für den Workflow ein, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a51ef-151">Type the SIP URI of additional managers to add to the workflow, and click **Add**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a51ef-p113">Jedem Benutzer, der als Manager einer Reaktionsgruppe bestimmt wurde, muss die Rolle CsResponseGroupManager zugewiesen sein. Falls Benutzern diese Rolle nicht zugewiesen ist, können sie keine Reaktionsgruppen verwalten.</span><span class="sxs-lookup"><span data-stu-id="a51ef-p113">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

16. <span data-ttu-id="a51ef-154">Klicken Sie unter **Schritt 2: Sprache auswählen** auf die Sprache, die für die Spracherkennung und Text-zu-Sprache verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a51ef-154">Under **Step 2 Select a Language**, click the language that you want to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="a51ef-155">Aktivieren Sie zum Konfigurieren einer Willkommensnachricht unter **Schritt 3: Willkommensnachricht konfigurieren** das Kontrollkästchen **Willkommensnachricht wiedergeben**, und führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="a51ef-155">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>
    
      - <span data-ttu-id="a51ef-156">Um die Willkommensnachricht als Text einzugeben, die für Anrufer in Sprache umgewandelt wird, klicken Sie auf **Text-zu-Sprache verwenden** und geben die Willkommensnachricht in das Textfeld ein.</span><span class="sxs-lookup"><span data-stu-id="a51ef-156">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a51ef-157">Verwenden Sie im eingegebenen Text keine HTML-Tags.</span><span class="sxs-lookup"><span data-stu-id="a51ef-157">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="a51ef-158">Andernfalls wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a51ef-158">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="a51ef-p115">Um eine aufgezeichnete WAV- (Wave) oder WMA-Datei (Windows Media Audio) für die Willkommensnachricht zu verwenden, klicken Sie auf **Auswählen einer Aufzeichnung**. Klicken Sie auf den Link **Aufzeichnung**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Audiodatei, und klicken Sie dann auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.</span><span class="sxs-lookup"><span data-stu-id="a51ef-p115">To use a wave (.wav) or Windows Media audio (.wma) file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a51ef-163">Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a51ef-163">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="a51ef-164">Ausführliche Informationen zu unterstützten Dateiformaten finden Sie unter <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a51ef-164">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

18. <span data-ttu-id="a51ef-165">Klicken Sie unter **Schritt 4: Geschäftszeiten angeben** im Feld **Ihre Zeitzone** auf die Zeitzone des Workflows.</span><span class="sxs-lookup"><span data-stu-id="a51ef-165">Under **Step 4 Specify Your Business Hours**, in **Your time zone**, click the time zone for the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a51ef-p117">Dies ist die Zeitzone, in der sich die Anrufer und Agents des Workflows befinden. Die Angabe wird verwendet, um die Öffnungszeiten zu berechnen. Wenn der Workflow z. B. für die mitteleuropäische Zeit konfiguriert wurde und der Workflow um 7:00 Uhr öffnen und um 23:00 Uhr schließen soll, werden die Zeiten 7:00 Uhr MEZ und 23:00 Uhr MEZ verwendet. (Die Zeiten müssen im 24-Stunden-Format eingegeben werden.)</span><span class="sxs-lookup"><span data-stu-id="a51ef-p117">The time zone is the time zone where the callers and agents of the workflow reside. It is used to calculate the open and close hours. For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M. and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 23:00 Eastern Time respectively. (You must enter the times in 24-hour time notation.)</span></span>

    
    </div>

19. <span data-ttu-id="a51ef-171">Sie haben folgende Möglichkeiten, um die gewünschten Geschäftszeiten anzugeben:</span><span class="sxs-lookup"><span data-stu-id="a51ef-171">Select the type of business hours schedule you want to use by doing one of the following:</span></span>
    
      - <span data-ttu-id="a51ef-172">Wenn Sie einen vordefinierten Zeitplan für die Geschäftszeiten verwenden möchten, klicken Sie auf **Verwenden eines vordefinierten Zeitplans**, und wählen Sie den gewünschten Zeitplan in der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="a51ef-172">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a51ef-173">Sie müssen mindestens einen vordefinierten Zeitplan erstellt haben, um diese Option auswählen zu können.</span><span class="sxs-lookup"><span data-stu-id="a51ef-173">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="a51ef-174">Sie erstellen vordefinierte Zeitpläne mit dem Cmdlet <STRONG>New-CSRgsHoursOfBusiness</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a51ef-174">You define preset schedules by using the <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet.</span></span> <span data-ttu-id="a51ef-175">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-optional-define-response-group-business-hours.md">(optional) definieren von Geschäftszeiten für Reaktionsgruppen in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a51ef-175">For details, see <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</A>.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a51ef-176">Wenn Sie einen vordefinierten Zeitplan verwenden, werden die Werte für <STRONG>Tag</STRONG>, <STRONG>Öffnen</STRONG> und <STRONG>Schließen</STRONG>, an denen die Reaktionsgruppe verfügbar ist, automatisch eingetragen.</span><span class="sxs-lookup"><span data-stu-id="a51ef-176">When you select a preset schedule, <STRONG>Day</STRONG>, <STRONG>Open</STRONG>, and <STRONG>Close</STRONG> are automatically filled with the days and hours that the response group is available.</span></span>

        
        </div>
    
      - <span data-ttu-id="a51ef-177">Klicken Sie auf **Verwenden eines benutzerdefinierten Zeitplans**, um einen benutzerdefinierten Zeitplan zu erstellen, der nur für diesen Workflow gilt.</span><span class="sxs-lookup"><span data-stu-id="a51ef-177">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="a51ef-178">Wenn Sie einen benutzerdefinierten Zeitplan für diesen Workflow erstellen, aktivieren Sie die Kontrollkästchen für die Wochentage, an denen die Reaktionsgruppe verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="a51ef-178">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="a51ef-179">Beim Erstellen eines benutzerdefinierten Zeitplans geben Sie über die Werte für **Öffnen** und **Schließen** den Zeitraum für jeden Wochentag ein, in dem die Reaktionsgruppe verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="a51ef-179">If you are creating a custom schedule, type the **Open** and **Close** hours for each day of the week that the response group available.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a51ef-p119">Die Werte für <STRONG>Öffnen</STRONG> und <STRONG>Schließen</STRONG> müssen im 24-Stunden-Format angegeben werden. Wenn Ihr Büro z. B. von 9 Uhr bis 17 Uhr geöffnet und mittags geschlossen ist, können Sie die Geschäftszeiten als <STRONG>Öffnen</STRONG> 9:00, <STRONG>Schließen</STRONG> 12:00, <STRONG>Öffnen</STRONG> 13:00 und <STRONG>Schließen</STRONG> 17:00 angeben.</span><span class="sxs-lookup"><span data-stu-id="a51ef-p119">The <STRONG>Open</STRONG> and <STRONG>Close</STRONG> hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as <STRONG>Open</STRONG> 9:00, <STRONG>Close</STRONG> 12:00, <STRONG>Open</STRONG> 13:00, and <STRONG>Close</STRONG> 17:00.</span></span>

    
    </div>

22. <span data-ttu-id="a51ef-182">Wenn Sie eine Nachricht wiedergeben möchten, wenn das Büro geschlossen ist, aktivieren Sie das Kontrollkästchen **Wiedergabe einer Nachricht, wenn sich die Reaktionsgruppe außerhalb der Geschäftszeiten befindet**, und geben Sie die Nachricht ein, indem Sie eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="a51ef-182">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="a51ef-183">Um die Nachricht als Text einzugeben, die für Anrufer in Sprache umgewandelt wird, klicken Sie auf **Text-zu-Sprache verwenden** und geben die Nachricht in das Textfeld ein.</span><span class="sxs-lookup"><span data-stu-id="a51ef-183">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a51ef-p120">Verwenden Sie im eingegebenen Text keine HTML-Tags. Andernfalls wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a51ef-p120">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="a51ef-p121">Um eine aufgezeichnete Audiodatei als Nachricht zu verwenden, klicken Sie auf **Auswählen einer Aufzeichnung**. Klicken Sie auf den Link **Aufzeichnung**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Datei, und klicken Sie auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.</span><span class="sxs-lookup"><span data-stu-id="a51ef-p121">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a51ef-190">Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a51ef-190">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="a51ef-191">Ausführliche Informationen zu unterstützten Audiodatei Formaten finden Sie unter <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a51ef-191">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

23. <span data-ttu-id="a51ef-192">Geben Sie an, wie nach Wiedergabe der Nachricht verfahren werden soll (sofern eine Nachricht konfiguriert wurde):</span><span class="sxs-lookup"><span data-stu-id="a51ef-192">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="a51ef-193">Klicken Sie auf **Verbindung trennen**, um die Verbindung zu trennen.</span><span class="sxs-lookup"><span data-stu-id="a51ef-193">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="a51ef-194">Um den Anruf an ein Voicemailsystem weiterzuleiten, klicken Sie auf **An Voicemail weiterleiten** und geben die Voicemailadresse ein.</span><span class="sxs-lookup"><span data-stu-id="a51ef-194">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="a51ef-195">Das Format für die Voicemail-Adresse lautet \<username\>@\<Domain Name\> (beispielsweise Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="a51ef-195">The format for the voice mail address is \<username\>@\<domainName\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="a51ef-196">Um den Anruf an einen anderen Benutzer weiterzuleiten, klicken Sie auf **An SIP-URI weiterleiten** und geben die Adresse eines Benutzers ein.</span><span class="sxs-lookup"><span data-stu-id="a51ef-196">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="a51ef-197">Das Format für die Benutzeradresse lautet \<username\>@\<Domain Name\>.</span><span class="sxs-lookup"><span data-stu-id="a51ef-197">The format for the user address is \<username\>@\<domainName\>.</span></span>
    
      - <span data-ttu-id="a51ef-198">Um den Anruf an eine andere Telefonnummer weiterzuleiten, klicken Sie auf **An Telefonnummer weiterleiten** und geben die Telefonnummer ein.</span><span class="sxs-lookup"><span data-stu-id="a51ef-198">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="a51ef-199">Das Format für die Telefonnummer lautet \<Number\>@\<Domain Name\> (beispielsweise + 14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="a51ef-199">The format for the telephone number is \<number\>@\<domainName\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="a51ef-200">Der Domänenname wird verwendet, um den Anrufer an das richtige Ziel weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="a51ef-200">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="a51ef-201">Aktivieren Sie unter **Schritt 5: Feiertage angeben** die Kontrollkästchen für einen oder mehrere Feiertagssätze, mit denen die Tage definiert werden, an denen die Reaktionsgruppe aufgrund eines Feiertags nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="a51ef-201">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a51ef-202">Sie müssen die für Sie geltenden Feiertage und Feiertagssätze definieren, bevor Sie den Workflow konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a51ef-202">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="a51ef-203">Verwenden Sie zum Definieren von Feiertagen und Feiertagssätzen die Cmdlets <STRONG>New-CsRgsHoliday</STRONG> und <STRONG>New-CsRgsHolidaySet</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a51ef-203">Use the <STRONG>New-CsRgsHoliday</STRONG> and <STRONG>New-CsRgsHolidaySet</STRONG> cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="a51ef-204">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(optional) definieren von Feiertagssätzen für Reaktionsgruppen in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a51ef-204">For details, see <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</A>.</span></span>

    
    </div>

25. <span data-ttu-id="a51ef-205">Wenn Sie an Feiertagen eine Nachricht wiedergeben möchten, aktivieren Sie das Kontrollkästchen **Wiedergabe einer Nachricht an Feiertagen**, und geben Sie die Nachricht an, indem Sie eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="a51ef-205">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="a51ef-206">Um die Nachricht als Text einzugeben, die für Anrufer in Sprache umgewandelt wird, klicken Sie auf **Text-zu-Sprache verwenden** und geben die Nachricht in das Textfeld ein.</span><span class="sxs-lookup"><span data-stu-id="a51ef-206">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a51ef-p127">Verwenden Sie im eingegebenen Text keine HTML-Tags. Andernfalls wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a51ef-p127">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="a51ef-p128">Um eine aufgezeichnete Audiodatei als Nachricht zu verwenden, klicken Sie auf **Auswählen einer Aufzeichnung**. Klicken Sie auf den Link **Aufzeichnung**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Datei, und klicken Sie auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.</span><span class="sxs-lookup"><span data-stu-id="a51ef-p128">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a51ef-213">Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a51ef-213">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="a51ef-214">Ausführliche Informationen zu unterstützten Audiodatei Formaten finden Sie unter <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a51ef-214">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

26. <span data-ttu-id="a51ef-215">Geben Sie an, wie nach Wiedergabe der Nachricht verfahren werden soll (sofern eine Nachricht konfiguriert wurde):</span><span class="sxs-lookup"><span data-stu-id="a51ef-215">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="a51ef-216">Klicken Sie auf **Verbindung trennen**, um die Verbindung zu trennen.</span><span class="sxs-lookup"><span data-stu-id="a51ef-216">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="a51ef-217">Um den Anruf an ein Voicemailsystem weiterzuleiten, klicken Sie auf **An Voicemail weiterleiten** und geben die Voicemailadresse ein.</span><span class="sxs-lookup"><span data-stu-id="a51ef-217">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="a51ef-218">Das Format für die Voicemail-Adresse lautet \<username\>@\<Domain Name\> (beispielsweise Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="a51ef-218">The format for the voice mail address is \<username\>@\<domainName\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="a51ef-219">Um den Anruf an einen anderen Benutzer weiterzuleiten, klicken Sie auf **An SIP-URI weiterleiten** und geben die Adresse eines Benutzers ein.</span><span class="sxs-lookup"><span data-stu-id="a51ef-219">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="a51ef-220">Das Format für die Benutzeradresse lautet \<username\>@\<Domain Name\>.</span><span class="sxs-lookup"><span data-stu-id="a51ef-220">The format for the user address is \<username\>@\<domainName\>.</span></span>
    
      - <span data-ttu-id="a51ef-221">Um den Anruf an eine andere Telefonnummer weiterzuleiten, klicken Sie auf **An Telefonnummer weiterleiten** und geben die Telefonnummer ein.</span><span class="sxs-lookup"><span data-stu-id="a51ef-221">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="a51ef-222">Das Format für die Telefonnummer lautet \<Number\>@\<Domain Name\> (beispielsweise + 14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="a51ef-222">The format for the telephone number is \<number\>@\<domainName\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="a51ef-223">Der Domänenname wird verwendet, um den Anrufer an das richtige Ziel weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="a51ef-223">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="a51ef-224">Wählen Sie unter **Schritt 6: Warteschleife konfigurieren** im Feld **Warteschleife für Anrufe auswählen** die Warteschleife aus, in der die Anrufer gehalten werden, bis ein Agent verfügbar wird.</span><span class="sxs-lookup"><span data-stu-id="a51ef-224">Under **Step 6 Configure a Queue**, in **Select the queue that will receive the calls**, select the queue that you want to hold callers until an agent becomes available.</span></span>

28. <span data-ttu-id="a51ef-225">Wählen Sie unter **Schritt 7: Wartemusik konfigurieren** aus, welche Musik Anrufer beim Warten auf einen Agent hören sollen, indem Sie einen der folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="a51ef-225">Under **Step 7 Configure Music on Hold**, choose the music you want callers to listen to while waiting for an agent by doing one of the following:</span></span>
    
      - <span data-ttu-id="a51ef-226">Klicken Sie auf **Standard verwenden**, um die Standardwartemusik zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a51ef-226">To use the default music-on-hold recording, click **Use default**.</span></span>
    
      - <span data-ttu-id="a51ef-p133">Klicken Sie auf **Auswählen einer Musikdatei**, um eine aufgezeichnete Audiodatei als Wartemusik zu verwenden. Klicken Sie auf den Link **Musikdatei**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Datei, und klicken Sie auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.</span><span class="sxs-lookup"><span data-stu-id="a51ef-p133">To use an audio file recording for the music on hold, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a51ef-231">Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a51ef-231">All user provided audio files must meet certain requirements.</span></span> <span data-ttu-id="a51ef-232">Ausführliche Informationen zu unterstützten Audiodatei Formaten finden Sie unter <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a51ef-232">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

29. <span data-ttu-id="a51ef-233">Klicken Sie auf **Bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="a51ef-233">Click **Deploy**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="a51ef-234">So verwenden Sie Windows PowerShell zum Erstellen oder Ändern eines Sammelanschluss-Workflows</span><span class="sxs-lookup"><span data-stu-id="a51ef-234">To use Windows PowerShell to create or modify a hunt group workflow</span></span>

1.  <span data-ttu-id="a51ef-235">Melden Sie sich als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a51ef-235">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="a51ef-236">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="a51ef-236">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a51ef-p135">Erstellen Sie die Ansage, die als Willkommensnachricht abgespielt werden soll, und speichern Sie sie in einer Variablen. Führen Sie an der Befehlszeile folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="a51ef-p135">Create the prompt to be played for the welcome message, and save it in a variable. At the command line, run:</span></span>
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="a51ef-239">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a51ef-239">For example:</span></span>
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a51ef-240">Verwenden Sie das Cmdlet <STRONG>Import-CsRgsAudioFile</STRONG>, um eine Audiodatei für die Ansage zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a51ef-240">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="a51ef-241">Ausführliche Informationen finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span><span class="sxs-lookup"><span data-stu-id="a51ef-241">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="a51ef-242">Rufen Sie die Identität der Warteschleife oder Frage ab, an die die Anrufe weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="a51ef-242">Get the identity of the queue or question where the calls will be directed.</span></span> <span data-ttu-id="a51ef-243">Führen Sie an der Befehlszeile folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="a51ef-243">At the command line, run:</span></span>
    
        $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
    
    <span data-ttu-id="a51ef-244">Ausführliche Informationen zum Erstellen der Warteschlange finden Sie unter [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue).</span><span class="sxs-lookup"><span data-stu-id="a51ef-244">For details about creating the queue, see [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue).</span></span>

5.  <span data-ttu-id="a51ef-p138">Definieren Sie die durchzuführende Standardaktion, wenn ein Workflow während der Geschäftszeiten geöffnet wird, und speichern Sie sie in einer Variablen. Führen Sie an der Befehlszeile folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="a51ef-p138">Define the default action to be taken when a workflow is opened during business hours, and save it in a variable. At the command line, run:</span></span>
    
        $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a51ef-p139">Für Workflows für Sammelanschlüsse muss der Anruf mit der Standardaktion an eine Warteschleife weitergeleitet werden. Dieser Parameter ist für aktive Workflows erforderlich, für inaktive Workflows dagegen nicht.</span><span class="sxs-lookup"><span data-stu-id="a51ef-p139">For hunt group workflows, the default action must direct the call to a queue. This is parameter is required for active workflows. It is not required for inactive workflows.</span></span>

    
    </div>
    
    <span data-ttu-id="a51ef-250">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a51ef-250">For example:</span></span>
    
        $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity

6.  <span data-ttu-id="a51ef-251">Wenn Sie Geschäftszeiten und Feiertage definieren möchten, müssen Sie diese erstellen, bevor Sie den Workflow erstellen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="a51ef-251">If you want to define business hours and holidays, you need to create them before you create or modify the workflow.</span></span> <span data-ttu-id="a51ef-252">Ausführliche Informationen finden Sie unter [(optional) definieren von Geschäftszeiten für Reaktionsgruppen in lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md) und [(optional) definieren von Feiertagssätzen für Reaktionsgruppen in lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md).</span><span class="sxs-lookup"><span data-stu-id="a51ef-252">For details, see [(Optional) Define Response Group business hours in Lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md) and [(Optional) Define Response Group holiday sets in Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md).</span></span>

7.  <span data-ttu-id="a51ef-253">Wenn Sie Ansagen für Anrufe wünschen, die außerhalb der Geschäftszeiten oder an Feiertagen empfangen werden, definieren Sie die Ansage mithilfe des **New-CsRgsPrompt**-Cmdlets, und definieren Sie mithilfe des **New-CsRgsCallAction**-Cmdlets die Aktion, die im Anschluss an die Ansage ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a51ef-253">If you want to have prompts for calls that are received out of business hours or on holidays, use the **New-CsRgsPrompt** cmdlet to define the prompt, and use the **New-CsRgsCallAction** to define the action to be taken after the prompt.</span></span> <span data-ttu-id="a51ef-254">Ausführliche Informationen finden Sie unter [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) und [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction).</span><span class="sxs-lookup"><span data-stu-id="a51ef-254">For details, see [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) and [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction).</span></span>

8.  <span data-ttu-id="a51ef-255">Rufen Sie den Dienstnamen für den lync Server Reaktionsgruppendienst ab, und weisen Sie ihn einer Variablen zu.</span><span class="sxs-lookup"><span data-stu-id="a51ef-255">Retrieve the service name for the Lync Server Response Group service and assign it to a variable.</span></span> <span data-ttu-id="a51ef-256">Führen Sie an der Befehlszeile folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="a51ef-256">At the command, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

9.  <span data-ttu-id="a51ef-257">Erstellen oder ändern Sie den Workflow.</span><span class="sxs-lookup"><span data-stu-id="a51ef-257">Create or modify the workflow.</span></span> <span data-ttu-id="a51ef-258">Verwenden Sie das **New-CsRgsWorkflow**-Cmdlet zum Erstellen eines Workflows.</span><span class="sxs-lookup"><span data-stu-id="a51ef-258">To create a workflow, use **New-CsRgsWorkflow**.</span></span> <span data-ttu-id="a51ef-259">Verwenden Sie das **Set-CsRgsWorkflow**-Cmdlet zum Ändern eines Workflows.</span><span class="sxs-lookup"><span data-stu-id="a51ef-259">To modify a workflow, use **Set-CsRgsWorkflow**.</span></span> <span data-ttu-id="a51ef-260">Geben Sie in die Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a51ef-260">At the command line, type:</span></span>
    
        $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-MangersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
    
    <span data-ttu-id="a51ef-261">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a51ef-261">For example:</span></span>
    
        $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a51ef-262">Allen Benutzer, die designierte Workflowmanager sind, muss die Rolle CsResponseGroupManager zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="a51ef-262">All users who are designated managers for workflows must be assigned the CsResponseGroupManager role.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a51ef-263">Ausführliche Informationen zu zusätzlichen optionalen Parametern finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">New-CsRgsWorkflow</A> oder <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">Festlegen von-CsRgsWorkflow</A></span><span class="sxs-lookup"><span data-stu-id="a51ef-263">For details about additional optional parameters, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">New-CsRgsWorkflow</A> or <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">Set-CsRgsWorkflow</A></span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a51ef-264">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a51ef-264">See Also</span></span>


[<span data-ttu-id="a51ef-265">Optional Definieren von Feiertagssätzen für Reaktionsgruppen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a51ef-265">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)  


[<span data-ttu-id="a51ef-266">Optional Definieren von Geschäftszeiten für Reaktionsgruppen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a51ef-266">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)  


[<span data-ttu-id="a51ef-267">New-CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="a51ef-267">New-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow)  
[<span data-ttu-id="a51ef-268">Gruppe-CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="a51ef-268">Set-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow)  
[<span data-ttu-id="a51ef-269">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="a51ef-269">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[<span data-ttu-id="a51ef-270">New-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="a51ef-270">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

