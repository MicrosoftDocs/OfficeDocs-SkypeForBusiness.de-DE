---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren von Einwahlkonferenzen für Besprechungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable dial-in conferencing for meetings
ms:assetid: 418dcf2d-c8d6-4b2c-b1ab-8723c7ef53e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688036(v=OCS.15)
ms:contentKeyID: 49733627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4600d5f978c553699029416951505c952f62bb62
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-dial-in-conferencing-for-meetings-in-lync-server-2013"></a><span data-ttu-id="38b43-102">Aktivieren oder Deaktivieren von Einwahlkonferenzen für Besprechungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38b43-102">Enable or disable dial-in conferencing for meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38b43-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="38b43-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="38b43-104">Im folgenden Verfahren wird beschrieben, wie Sie Benutzern die Teilnahme an einer Besprechung mithilfe von Einwahl ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="38b43-104">The following procedure describes how to allow user to join a meeting using dial-in.</span></span>

<div>

## <a name="to-enable-or-disable-dial-in-conferencing"></a><span data-ttu-id="38b43-105">So aktivieren oder deaktivieren Sie Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="38b43-105">To enable or disable dial-in conferencing</span></span>

1.  <span data-ttu-id="38b43-106">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="38b43-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="38b43-107">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="38b43-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="38b43-108">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="38b43-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="38b43-109">Klicken Sie in der linken Navigationsleiste auf **Konferenzen** , und klicken Sie dann auf **konferenzrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="38b43-109">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="38b43-110">Wählen Sie in der Liste der Konferenzrichtlinien die Richtlinie aus, für die Sie Einwahlkonferenzen zulassen möchten, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="38b43-110">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="38b43-p102">Wenn Sie Benutzern erlauben möchten, per Einwahl an einer Besprechung teilzunehmen, aktivieren Sie das Kontrollkästchen **PSTN-Einwahlkonferenzen aktivieren**. In der Standardeinstellung können Benutzer sich über das Festnetz (Public Switched Telephone Network, PSTN) in Besprechungen einwählen.</span><span class="sxs-lookup"><span data-stu-id="38b43-p102">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>

6.  <span data-ttu-id="38b43-113">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="38b43-113">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

