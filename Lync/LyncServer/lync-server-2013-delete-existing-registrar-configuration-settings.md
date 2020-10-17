---
title: 'Lync Server 2013: Löschen vorhandener Registrierungsstellen-Konfigurationseinstellungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete existing Registrar configuration settings
ms:assetid: ae43cd75-cae4-4f78-b037-779a2cdb583b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182571(v=OCS.15)
ms:contentKeyID: 48185132
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a0624806ba8ed2f10bc0c7cffbf1e8879209c66
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525602"
---
# <a name="delete-existing-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="bbf5f-102">Löschen vorhandener Registrierungsstellen-Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bbf5f-102">Delete existing Registrar configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bbf5f-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="bbf5f-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="bbf5f-104">Führen Sie die folgenden Schritte aus, um eine Registrierung zu löschen.</span><span class="sxs-lookup"><span data-stu-id="bbf5f-104">Follow these steps to delete a Registrar.</span></span>

<div>

## <a name="to-delete-registrar-configuration-settings"></a><span data-ttu-id="bbf5f-105">So löschen Sie Registrierungs Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="bbf5f-105">To delete Registrar configuration settings</span></span>

1.  <span data-ttu-id="bbf5f-106">Melden Sie sich von einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe (oder gleichwertigen Benutzerrechten) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="bbf5f-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="bbf5f-107">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="bbf5f-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bbf5f-108">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bbf5f-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bbf5f-109">Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Registrierung**.</span><span class="sxs-lookup"><span data-stu-id="bbf5f-109">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="bbf5f-110">Geben Sie auf der Seite **Registrierung** im Suchfeld Teile oder den vollständigen Namen der Registrierung ein, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="bbf5f-110">On the **Registrar** page, and in the search field, type all or part of the name of the Registrar you want to delete.</span></span>

5.  <span data-ttu-id="bbf5f-111">Klicken Sie in der Liste auf die gewünschte Registrierung, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="bbf5f-111">In the list, click the Registrar that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="bbf5f-112">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bbf5f-112">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="bbf5f-113">Entfernen von Registrierungsstellen-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="bbf5f-113">Removing Registrar Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="bbf5f-114">Sie können die Registrierungsstellen-Konfigurationseinstellungen mit Windows PowerShell und dem Cmdlet **Remove-CsProxyConfiguration** löschen.</span><span class="sxs-lookup"><span data-stu-id="bbf5f-114">You can delete the Registrar configuration settings by using Windows PowerShell and the **Remove-CsProxyConfiguration** cmdlet.</span></span> <span data-ttu-id="bbf5f-115">Sie können dieses Cmdlet in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="bbf5f-115">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="bbf5f-116">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="bbf5f-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-set-of-registrar-security-settings"></a><span data-ttu-id="bbf5f-117">So entfernen Sie eine bestimmte Gruppe mit Registrierungssicherheitseinstellungen</span><span class="sxs-lookup"><span data-stu-id="bbf5f-117">To remove a specific set of Registrar security settings</span></span>

  - <span data-ttu-id="bbf5f-118">Mithilfe des folgenden Befehls werden die auf den Edgeserver "atl-edge-011.litwareinc.com" angewendeten Sicherheitseinstellungen für die Registrierung entfernt:</span><span class="sxs-lookup"><span data-stu-id="bbf5f-118">The following command removes the Registrar security settings applied to the edge Server atl-edge-011.litwareinc.com:</span></span>
    
        Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a><span data-ttu-id="bbf5f-119">So entfernen Sie alle Sicherheitseinstellungen für die Registrierung, die auf Standortebene angewendet werden</span><span class="sxs-lookup"><span data-stu-id="bbf5f-119">To remove all of the Registrar security settings applied to the site scope</span></span>

  - <span data-ttu-id="bbf5f-120">Mithilfe des folgenden Befehls werden alle auf den Registrierungsdienst angewendeten Sicherheitseinstellungen für die Registrierung entfernt:</span><span class="sxs-lookup"><span data-stu-id="bbf5f-120">The following command removes all the Registrar security settings applied to the Registrar service:</span></span>
    
        Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a><span data-ttu-id="bbf5f-121">So entfernen Sie alle Sicherheitseinstellungen für die Registrierung, die die NTLM-Authentifizierung zulassen</span><span class="sxs-lookup"><span data-stu-id="bbf5f-121">To remove all of the Registrar security settings that allow NTLM authentication</span></span>

  - <span data-ttu-id="bbf5f-122">Mithilfe des folgenden Befehls werden alle Sicherheitseinstellungen für die Registrierung gelöscht, die die Verwendung von NTLM für die Clientauthentifizierung zulassen:</span><span class="sxs-lookup"><span data-stu-id="bbf5f-122">The following command deletes all the Registrar security settings that allow the use of NTLM for client authentication:</span></span>
    
        Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration

</div>

<span data-ttu-id="bbf5f-123">Ausführliche Informationen finden Sie unter [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration).</span><span class="sxs-lookup"><span data-stu-id="bbf5f-123">For details, see [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

