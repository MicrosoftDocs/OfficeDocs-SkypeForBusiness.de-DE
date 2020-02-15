---
title: 'Lync Server 2013: Einrichten von Kennwörtern für das Kerberos-Authentifizierungs Konto'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication account passwords
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412870(v=OCS.15)
ms:contentKeyID: 48185167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0342c83090dee6cbe021a400acd87e557860518b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037575"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a><span data-ttu-id="f72bf-102">Einrichten von Kennwörtern für das Kerberos-Authentifizierungs Konto in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f72bf-102">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f72bf-103">_**Letztes Änderungsstand des Themas:** 2010-11-03_</span><span class="sxs-lookup"><span data-stu-id="f72bf-103">_**Topic Last Modified:** 2010-11-03_</span></span>

<span data-ttu-id="f72bf-104">Nach dem Erstellen des Computerobjekts für das Kerberos-Authentifizierungskonto können Sie das Kennwort für das Konto einrichten.</span><span class="sxs-lookup"><span data-stu-id="f72bf-104">After you create the computer object for the Kerberos authentication account, you can set up the password for the account.</span></span> <span data-ttu-id="f72bf-105">Sie führen das Windows PowerShell-Cmdlet aus, um das Kennwort des Kerberos-Kontos auf einem Server festzulegen.</span><span class="sxs-lookup"><span data-stu-id="f72bf-105">You run the Windows PowerShell cmdlet for setting the Kerberos account password on one server.</span></span> <span data-ttu-id="f72bf-106">Sie können das Kennwort für das Objekt festlegen, das Sie für die Kerberos-Authentifizierung erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="f72bf-106">You can set the password on the object that you created for the Kerberos authentication.</span></span> <span data-ttu-id="f72bf-107">Das Kennwort kann auf einen bekannten Wert festgelegt werden, ist aber standardmäßig ein beliebiges Kennwort.</span><span class="sxs-lookup"><span data-stu-id="f72bf-107">The password can be set to a known value, but by default is a random password.</span></span> <span data-ttu-id="f72bf-108">Das Kennwort steht allen Kerberos-Authentifizierungsquellen zur Verfügung, die dieses Konto verwenden.</span><span class="sxs-lookup"><span data-stu-id="f72bf-108">The password is available to all Kerberos authentication sources that use the account.</span></span> <span data-ttu-id="f72bf-109">Verwenden Sie Windows PowerShell-Cmdlets zum Einrichten und Verwalten von Kerberos-Kontokennwörtern.</span><span class="sxs-lookup"><span data-stu-id="f72bf-109">You use Windows PowerShell cmdlets to set up and manage Kerberos account passwords.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f72bf-110">Das Kerberos-Kontoobjekt ist ein Computerobjekt, verwendet jedoch den Useraccount-Parameter für Vorgänge in den Windows PowerShell-Cmdlets, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="f72bf-110">The Kerberos account object is a computer object, but uses the UserAccount parameter for operations in the Windows PowerShell cmdlets that are referenced.</span></span> <span data-ttu-id="f72bf-111">Beachten Sie, dass dies kein Fehler, sondern das beabsichtigte Verhalten des Cmdlets ist, wenn es für die Erstellung und Verwaltung von Kerberos-Konten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f72bf-111">Note that this is not a mistake, but the intended behavior of the cmdlet when used with the Kerberos account creation and maintenance.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f72bf-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f72bf-112">In This Section</span></span>

  - [<span data-ttu-id="f72bf-113">Festlegen eines Kennworts für das Kerberos-Authentifizierungs Konto auf einem Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f72bf-113">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [<span data-ttu-id="f72bf-114">Synchronisieren eines Kennworts für das Kerberos-Authentifizierungs Konto mit IIS in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f72bf-114">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

