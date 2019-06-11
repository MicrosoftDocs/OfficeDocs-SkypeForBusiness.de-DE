---
title: 'Lync Server 2013: Konfigurieren der Benutzerkontoeinstellungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure user account settings
ms:assetid: b7c74ecc-b924-4efc-8a56-3a5f94a9ef13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412896(v=OCS.15)
ms:contentKeyID: 48185200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4d06405d2f80aef5decb69d564ae399401d4328
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-user-account-settings-in-lync-server-2013"></a><span data-ttu-id="f961a-102">Konfigurieren der Benutzerkontoeinstellungen  in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f961a-102">Configure user account settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f961a-103">_**Letztes Änderungsdatum des Themas:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="f961a-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="f961a-104">Teilnehmer an Einwahlkonferenzen geben ihre Telefonnummer oder Durchwahl sowie eine PIN ein, um als authentifizierte Benutzer an Konferenzen teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="f961a-104">Dial-in users enter their phone number or extension and a PIN to join conferences as authenticated users.</span></span> <span data-ttu-id="f961a-105">Für die Authentifizierung ist der in lync Server-Benutzerkonten angegebene Telefon Leitungs- **URI** erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f961a-105">The telephony **Line URI** specified on Lync Server user accounts is required for authentication.</span></span>

<span data-ttu-id="f961a-106">In diesem Thema wird beschrieben, wie Sie einem einzelnen Benutzerkonto einen **Anschluss-URI** zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f961a-106">The procedure in this topic describes how to assign a **Line URI** for a single user account.</span></span> <span data-ttu-id="f961a-107">Wenn Sie mehreren Benutzerkonten einen **Anschluss-URI** zuweisen möchten, können Sie ein Skript erstellen, das das Cmdlet **Set-CsUser** verwendet.</span><span class="sxs-lookup"><span data-stu-id="f961a-107">If you need to assign a **Line URI** for multiple user accounts, you can create a script that uses the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="f961a-108">Details zur Verwendung eines Beispielskripts zum Zuweisen von **Leitungs-URI** zu mehreren Benutzerkonten finden Sie unter "Zuweisen von [http://go.microsoft.com/fwlink/p/?linkId=196945](http://go.microsoft.com/fwlink/p/?linkid=196945)Leitungs-URIs zu mehreren Benutzern" unter.</span><span class="sxs-lookup"><span data-stu-id="f961a-108">For details about using a sample script to assign **Line URI** to multiple user accounts, see "Assign Line URIs to Multiple Users" at [http://go.microsoft.com/fwlink/p/?linkId=196945](http://go.microsoft.com/fwlink/p/?linkid=196945).</span></span>

<div>

## <a name="to-configure-user-account-settings"></a><span data-ttu-id="f961a-109">So konfigurieren Sie die Benutzerkontoeinstellungen</span><span class="sxs-lookup"><span data-stu-id="f961a-109">To configure user account settings</span></span>

1.  <span data-ttu-id="f961a-110">Melden Sie sich beim Computer als Mitglied der Gruppe „RTCUniversalServerAdmins“ oder als Benutzer mit der Rolle **Cs-UserAdministrator** oder **CsAdministrator** an.</span><span class="sxs-lookup"><span data-stu-id="f961a-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-UserAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="f961a-111">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f961a-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f961a-112">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f961a-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f961a-113">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="f961a-113">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="f961a-114">Geben Sie in das Suchfeld den Namen des Benutzers ein, den Sie für Einwahlkonferenzen konfigurieren möchten, oder klicken Sie auf **Filter hinzufügen**, um Suchfelder anzugeben und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="f961a-114">In the search field, type the name of the user you want to configure for dial-in conferencing or click **Add filter** to specify search fields, and then click **Find**.</span></span>

5.  <span data-ttu-id="f961a-115">Doppelklicken Sie auf den Benutzernamen, um das Dialogfeld **lync Server-Benutzer bearbeiten** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f961a-115">Double-click the user name to open the **Edit Lync Server User** dialog box.</span></span>

6.  <span data-ttu-id="f961a-116">Geben Sie unter **Telefonie** in das Feld **Anschluss-URI** eine eindeutige, normalisierte Telefonnummer ein (beispielsweise tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="f961a-116">Under **Telephony**, in the **Line URI** field, type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f961a-117">Sie können <STRONG>Anschluss-URI</STRONG> nur angeben, wenn <STRONG>Telefonie</STRONG> auf <STRONG>Nur von PC zu PC</STRONG>, <STRONG>Enterprise-VoIP</STRONG>, <STRONG>Remoteanrufsteuerung</STRONG> oder <STRONG>Nur Remoteanrufsteuerung</STRONG> festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f961a-117">You can specify <STRONG>Line URI</STRONG> only if <STRONG>Telephony</STRONG> is set to <STRONG>PC-to-PC only</STRONG>, <STRONG>Enterprise Voice</STRONG>, <STRONG>Remote call control</STRONG> or <STRONG>Remote call control only</STRONG>.</span></span>

    
    </div>

7.  <span data-ttu-id="f961a-118">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="f961a-118">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

