---
title: 'Lync Server 2013: Aktivieren von lync-Benutzern für die Remoteanrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Lync users for remote call control
ms:assetid: f39bc10d-034c-4875-a0b8-554e1109e7e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615048(v=OCS.15)
ms:contentKeyID: 48185795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7e165efe4e9b679c5464a35aac1c4130840b801
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-lync-users-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="f8417-102">Aktivieren von lync-Benutzern für die Remoteanrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8417-102">Enable Lync users for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8417-103">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="f8417-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="f8417-104">Sie können lync-Benutzer für die Remoteanrufsteuerung mithilfe von in-Band-Bereitstellung-Richtlinien konfigurieren, die Server basiert sind.</span><span class="sxs-lookup"><span data-stu-id="f8417-104">You can configure Lync users for remote call control by using in-band provisioning policies that are server-based.</span></span> <span data-ttu-id="f8417-105">Sie können die Einstellungen für die in-Band-Konfiguration mithilfe von lync Server-Systemsteuerung oder der lync Server-Verwaltungsshell Befehlszeilenschnittstelle verwalten.</span><span class="sxs-lookup"><span data-stu-id="f8417-105">You can manage in-band provisioning settings by using Lync Server Control Panel or the Lync Server Management Shell command-line interface.</span></span> <span data-ttu-id="f8417-106">Diese Tools ersetzen das WMI-Snap-in (Windows Management Instrumentation), das zum Verwalten von Gruppenrichtlinieneinstellungen in früheren Versionen verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="f8417-106">These tools replace the Windows Management Instrumentation (WMI) snap-in that was used to manage Group Policy settings in earlier releases.</span></span>

<span data-ttu-id="f8417-107">Wenn Sie es vorziehen, Benutzern die Konfiguration Ihrer eigenen Einstellungen für die Remoteanrufsteuerung in lync zu ermöglichen, können Sie die Einstellungen für die Remoteanrufsteuerung für Benutzer auf dem Server konfigurieren, ohne den URI und die Werte für den **Anschluss** - **URI** anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f8417-107">If you prefer to let users to configure their own remote call control settings in Lync, you can configure remote call control settings for users on the server without specifying **Line Server URI** and **Line URI** values.</span></span> <span data-ttu-id="f8417-108">Stellen Sie sicher, dass Sie den entsprechenden **Anschluss Server-URI** und die Werte für den **Anschluss-URI** Ihren Benutzern mitteilen, und geben Sie den Benutzern Anweisungen zum Konfigurieren dieser Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="f8417-108">Be sure that you communicate the appropriate **Line Server URI** and **Line URI** values to your users, and provide your users with the instructions to configure these settings.</span></span> <span data-ttu-id="f8417-109">Informationen zum manuellen Konfigurieren der Remoteanrufsteuerung in lync Server finden Sie unter "Festlegen von Telefonnummern" <https://go.microsoft.com/fwlink/p/?linkid=210132> in der lync-Client Dokumentation auf der Microsoft Office Website.</span><span class="sxs-lookup"><span data-stu-id="f8417-109">For the procedure to manually configure remote call control in Lync Server, see "Set Phones options and numbers" at <https://go.microsoft.com/fwlink/p/?linkid=210132> in the Lync client documentation on the Microsoft Office website.</span></span>

<span data-ttu-id="f8417-110">Wenn Sie über eine vorhandene Communications Server 2007 R2-oder Communications Server 2007-Bereitstellung verfügen, verwenden Communicator 2007 R2 und Communicator 2007 Clients weiterhin Gruppenrichtlinien während der parallelen Migration.</span><span class="sxs-lookup"><span data-stu-id="f8417-110">If you have an existing Communications Server 2007 R2 or Communications Server 2007 deployment, Communicator 2007 R2 and Communicator 2007 clients will continue to use Group Policy during side-by-side migration.</span></span> <span data-ttu-id="f8417-111">Wenn Sie jedoch möchten, dass Richtlinieneinstellungen auf lync-Clients übertragen werden, müssen Sie die entsprechenden lync Server Einstellungen für die in-Band-Konfiguration konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f8417-111">However, if you want policy settings to carry over to Lync clients, you need to configure the equivalent Lync Server in-band provisioning settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f8417-112">Wenn Sie einen Benutzer für die Remoteanrufsteuerung aktivieren möchten, müssen Sie dem Benutzer sowohl einen Anschluss-URI als auch einen Anschluss Server-URI bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f8417-112">To enable a user for remote call control, you need to provide the user with both a Line URI and a Line Server URI.</span></span> <span data-ttu-id="f8417-113">Wie unter <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Bereitstellungsaufgaben für die Remoteanrufsteuerung in lync Server 2013</A>beschrieben, müssen Sie sicherstellen, dass Sie die für das Gateway erforderliche Syntax für diese Einstellungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="f8417-113">As described in <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Deployment tasks for remote call control in Lync Server 2013</A>, you need to be sure to use the syntax that is required by the gateway for these settings.</span></span><BR><span data-ttu-id="f8417-114">Stellen Sie sicher, dass die Domäne im Linien Server-URI mit der Zieldomäne identisch ist, die Sie im Parameter MatchUri angegeben haben, als Sie die statische Route zum Gateway konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="f8417-114">Be sure that the domain in the Line Server URI is the same as the destination domain that you specified in the MatchUri parameter when you configured the static route to the gateway.</span></span><BR><span data-ttu-id="f8417-115">Der Anschluss-URI gibt die Telefonnummer an, die dem Benutzer im E. 164-Format zugewiesen ist, mit dem Präfix "Tel:" (beispielsweise Tel: + 14255550150).</span><span class="sxs-lookup"><span data-stu-id="f8417-115">The Line URI specifies the phone number assigned to the user in E.164 format, with the "TEL:" prefix (for example, tel:+14255550150).</span></span> <span data-ttu-id="f8417-116">Wenn Sie eine Durchwahlnummer konfigurieren möchten, lautet das Format Tel: + 14255550150; ext = 111.</span><span class="sxs-lookup"><span data-stu-id="f8417-116">If you want to configure an extension number, then the format is tel:+14255550150;ext=111.</span></span> <span data-ttu-id="f8417-117">Wenn Sie den Anschluss-URI des Benutzers zuvor konfiguriert haben und der Wert nicht geändert wurde, müssen Sie den Anschluss-URI nicht angeben, wenn Sie den Benutzer für die Remoteanrufsteuerung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f8417-117">If you previously configured the user’s Line URI and the value has not changed, you do not need to specify the Line URI when you enable the user for remote call control.</span></span>



</div>

<div>

## <a name="to-enable-remote-call-control-for-lync-enabled-users-by-using-management-shell"></a><span data-ttu-id="f8417-118">So aktivieren Sie die Remoteanrufsteuerung für lync-aktivierte Benutzer mithilfe von Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="f8417-118">To enable remote call control for Lync-enabled users by using Management Shell</span></span>

1.  <span data-ttu-id="f8417-119">Melden Sie sich an einem Computer an, auf dem lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder als rollenbasierte zugriffssteuerungsrolle installiert ist, der Sie das Cmdlet " **CsUser** " zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="f8417-119">Log on to a computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or as a role-based access control role to which you have assigned the **Set-CsUser** cmdlet.</span></span>

2.  <span data-ttu-id="f8417-120">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="f8417-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f8417-121">Führen Sie die folgenden Schritte aus, um das Cmdlet " **CsUser** " zum Konfigurieren der Remoteanrufsteuerung für einen vorhandenen lync-aktivierten Benutzer zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="f8417-121">To use the **Set-CsUser** cmdlet to configure remote call control for an existing Lync-enabled user, do the following:</span></span>
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    <span data-ttu-id="f8417-122">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f8417-122">For example:</span></span>
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

</div>

<div>

## <a name="to-configure-users-for-remote-call-control-by-using-lync-server-control-panel"></a><span data-ttu-id="f8417-123">So konfigurieren Sie Benutzer für die Remoteanrufsteuerung mithilfe von lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="f8417-123">To configure users for remote call control by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f8417-124">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="f8417-124">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f8417-125">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f8417-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f8417-126">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f8417-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f8417-127">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="f8417-127">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="f8417-128">Geben Sie im Feld **Benutzer suchen** alle (oder den ersten Teil) des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens (Security Accounts Manager), der SIP-Adresse oder des Anschluss-URI (Uniform Resource Identifier) des gewünschten Benutzerkontos ein, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="f8417-128">In the **Search users** box, type all (or the first portion) of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="f8417-129">Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="f8417-129">In the table, click the user account that you want to modify.</span></span>

6.  <span data-ttu-id="f8417-130">Klicken Sie im Menü **Bearbeiten** auf **Ändern**.</span><span class="sxs-lookup"><span data-stu-id="f8417-130">On the **Edit** menu, click **Modify**.</span></span>

7.  <span data-ttu-id="f8417-131">Führen Sie in **Telefonie**einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f8417-131">In **Telephony**, do one of the following:</span></span>
    
      - <span data-ttu-id="f8417-132">Klicken Sie auf **Remoteanrufsteuerung**, um die Remoteanrufsteuerung zu aktivieren, um dem Benutzer die Steuerung des PBX-Telefons (Private Branch Exchange) aus lync 2013 zu ermöglichen, um PC-zu-PC-Audioanrufe und PC-zu-Telefonanrufe zu tätigen.</span><span class="sxs-lookup"><span data-stu-id="f8417-132">To enable remote call control to enable the user to control their private branch exchange (PBX) phone from Lync 2013 to make PC-to-PC audio calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="f8417-133">Geben Sie unter **Leitungs-URI**die Telefonnummer des Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="f8417-133">In **Line URI**, specify the telephone number of the user.</span></span> <span data-ttu-id="f8417-134">Geben Sie unter **Anschluss Server-URI**den SIP-URI des SIP/CSTA-Gateways an.</span><span class="sxs-lookup"><span data-stu-id="f8417-134">In **Line Server URI**, specify the SIP URI of the SIP/CSTA gateway.</span></span>
    
      - <span data-ttu-id="f8417-135">Um die Remoteanrufsteuerung zu aktivieren, aber PC-zu-PC-Audioanrufe zu deaktivieren und nur dem Benutzer zu ermöglichen, sein PBX-Telefon von lync 2013 zu steuern, um Anrufe von PC zu Telefon zu tätigen, klicken Sie **nur auf Remoteanrufsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="f8417-135">To enable remote call control, but disable PC-to-PC audio calls, and to enable only the user to control their PBX phone from Lync 2013 to make PC-to-phone calls, click **Remote call control only**.</span></span> <span data-ttu-id="f8417-136">Geben Sie unter **Leitungs-URI**die Telefonnummer des Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="f8417-136">In **Line URI**, specify the telephone number of the user.</span></span> <span data-ttu-id="f8417-137">Geben Sie unter **Anschluss Server-URI**den SIP-URI des SIP/CSTA-Gateways an.</span><span class="sxs-lookup"><span data-stu-id="f8417-137">In **Line Server URI**, specify the SIP URI of the SIP/CSTA gateway.</span></span>

8.  <span data-ttu-id="f8417-138">Wenn Sie fertig sind, klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="f8417-138">When you are finished, click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

