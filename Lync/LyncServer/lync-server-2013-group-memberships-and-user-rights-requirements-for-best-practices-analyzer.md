---
title: Gruppenmitgliedschaften und Benutzerrechte Anforderungen für Best Practices Analyzer
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group memberships and user rights requirements for Best Practices Analyzer
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48185869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9561736fc6dce1649d0a3dd29e15a7d88500a38
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="4461d-102">Gruppenmitgliedschaften und Benutzerrechte Anforderungen für Best Practices Analyzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4461d-102">Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4461d-103">_**Letztes Änderungsdatum des Themas:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="4461d-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="4461d-104">Damit Sie Best Practices Analyzer erfolgreich ausführen können, muss das Benutzerkonto, das Sie für die Anmeldung verwenden, ein Mitglied der Gruppe Administratoren auf dem lokalen Computer sein.</span><span class="sxs-lookup"><span data-stu-id="4461d-104">To successfully run Best Practices Analyzer, the user account that you use to log on must be a member of the Administrators group on the local computer.</span></span> <span data-ttu-id="4461d-105">Darüber hinaus muss das Benutzerkonto ein Mitglied der folgenden Gruppen sein, um die Umgebung zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="4461d-105">Additionally, to scan your environment, the user account must be a member of the following groups:</span></span>

  - <span data-ttu-id="4461d-106">**Domänenadministratoren**   , um Informationen zu Active Directory-Domänendiensten aufzulisten und die WMI-Anbieter (Windows Management Instrumentation) auf Domänencontrollern und globalen Katalogservern aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="4461d-106">**Domain Admins**   To enumerate Active Directory Domain Services information and to call the Windows Management Instrumentation (WMI) providers on domain controllers and global catalog servers.</span></span>

  - <span data-ttu-id="4461d-107">**Administratoren**   , die für jeden lync Server 2013-internen Computer und jeden Edgeserver erforderlich sind, um die WMI-Anbieter (Windows Management Instrumentation) anzurufen und auf die Registrierung zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="4461d-107">**Administrators**   Required on each Lync Server 2013 internal computer and each Edge Server to call the Windows Management Instrumentation (WMI) providers and to access the registry.</span></span>

  - <span data-ttu-id="4461d-108">**RTCUniversalReadOnlyAdmins**   vollständig oder delegiert lesen Sie nur lync Server 2013-Administratorrechte.</span><span class="sxs-lookup"><span data-stu-id="4461d-108">**RTCUniversalReadOnlyAdmins**   Full or delegated read only Lync Server 2013 administrative rights.</span></span>

  - <span data-ttu-id="4461d-109">**Exchange-Administrator**   "nur anzeigen" vollständiger oder Delegierter Exchange-Administrator "nur anzeigen" für die Microsoft Exchange-Organisation.</span><span class="sxs-lookup"><span data-stu-id="4461d-109">**Exchange View Only Administrator**   Full or delegated Exchange View Only Administrator on the Microsoft Exchange organization.</span></span>

<span data-ttu-id="4461d-110">Wenn Ihr Benutzerkonto nicht über ausreichende Benutzerrechte verfügt, haben Sie zwei Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="4461d-110">If your user account does not have sufficient user rights, you have two options:</span></span>

  - <span data-ttu-id="4461d-111">Verwenden Sie an einer Eingabeaufforderung den Befehl **runas** , um das Tool unter einem Konto auszuführen, das über genügend Benutzerrechte verfügt.</span><span class="sxs-lookup"><span data-stu-id="4461d-111">At a command prompt, use the **runas** command to run the tool under an account that does have sufficient user rights.</span></span> <span data-ttu-id="4461d-112">Die Syntax lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="4461d-112">The syntax is as follows:</span></span>
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - <span data-ttu-id="4461d-113">Setzen Sie auf der Seite **mit Active Directory verbinden** die Anmeldeinformationen für die Konten, die Sie zum Ausführen von Best Practices Analyzer verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="4461d-113">On the **Connect to Active Directory** page, set the credentials for the accounts that you plan to use to run Best Practices Analyzer.</span></span> <span data-ttu-id="4461d-114">Klicken Sie auf **Erweiterte Anmeldeoptionen anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="4461d-114">Click **Show advanced login options**.</span></span> <span data-ttu-id="4461d-115">Sie können drei Konten eingeben: eine zum Herstellen einer Verbindung mit Active Directory-Domänendiensten, eine zum Herstellen einer Verbindung mit lync Server 2013-Edgeserver und eine für die Verbindung zu den Exchange-Servern.</span><span class="sxs-lookup"><span data-stu-id="4461d-115">You can enter three accounts: one for connecting to Active Directory Domain Services, one for connecting to Lync Server 2013 Edge Servers, and one for connecting to the Exchange Servers.</span></span> <span data-ttu-id="4461d-116">Wenn Sie keines dieser Konten angeben, wird das Benutzerkonto verwendet, das Sie für die Anmeldung und die Ausführung von Best Practices Analyzer verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="4461d-116">If you do not specify any of these accounts, the user account that you used to log on and run Best Practices Analyzer is used.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

