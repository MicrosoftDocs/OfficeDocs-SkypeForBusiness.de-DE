---
title: 'Lync Server 2013: Einrichten der Kerberos-Authentifizierung'
description: 'Lync Server 2013: Einrichten der Kerberos-Authentifizierung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication
ms:assetid: dd8009ef-6265-4cc0-b2c7-e474cd1f4b09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398976(v=OCS.15)
ms:contentKeyID: 48185601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb461968bc073edbfe640f609257f3e84c192461
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577231"
---
# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="a12ae-103">Einrichten der Kerberos-Authentifizierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a12ae-103">Setting up Kerberos authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a12ae-104">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="a12ae-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="a12ae-105">Lync Server 2013 unterstützt NTLM-und Kerberos-Authentifizierung für Webdienste.</span><span class="sxs-lookup"><span data-stu-id="a12ae-105">Lync Server 2013 supports NTLM and Kerberos authentication for Web Services.</span></span> <span data-ttu-id="a12ae-106">Office Communications Server 2007 und Office Communications Server 2007 R2 verwendet die standardmäßigen RTCComponentService und RTCService als Benutzerkonten zum Ausführen der Webdienste Anwendungspools, sodass ein Dienstprinzipalname (Service Principal Name, SPN) den Benutzerkonten zugewiesen und als Authentifizierungs Prinzipal fungieren kann.</span><span class="sxs-lookup"><span data-stu-id="a12ae-106">Office Communications Server 2007 and Office Communications Server 2007 R2 used the default RTCComponentService and RTCService as the user accounts to run the Web Services application pools, allowing for a service principal name (SPN) to be assigned to the user accounts and to act as the authentication principal.</span></span> <span data-ttu-id="a12ae-107">Lync Server verwendet Network Service zum Ausführen von Webdienste, und Network Service kann keine SPNs zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="a12ae-107">Lync Server uses NetworkService to run Web Services and NetworkService cannot have SPNs assigned to it.</span></span>

<span data-ttu-id="a12ae-108">Um das Problem zu beheben, dass keine Active Directory-Objekte zum Speichern der SPNs zur Verfügung stehen, können lync Server-Systemsteuerung Computerkonto-Objekte zu diesem Zweck verwenden.</span><span class="sxs-lookup"><span data-stu-id="a12ae-108">To solve the issue of not having Active Directory objects to hold the SPNs, Lync Server Control Panel can use computer account objects for this purpose.</span></span> <span data-ttu-id="a12ae-109">Die Computerkontoobjekte können die Dienstprinzipalnamen enthalten und unterliegen keinem Kennwortablauf, was bei der Verwendung von Benutzerkonten in früheren Versionen ein Problem darstellte.</span><span class="sxs-lookup"><span data-stu-id="a12ae-109">The computer account objects can hold the SPNs and are not subject to password expiration, which was an issue with using user accounts in previous versions.</span></span>

<span data-ttu-id="a12ae-110">Verwenden Sie Windows PowerShell-Cmdlets, um die Computerobjekte für die Bereitstellung der Kerberos-Authentifizierung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a12ae-110">You use Windows PowerShell cmdlets to configure the computer objects to provide Kerberos authentication.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a12ae-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a12ae-111">In This Section</span></span>

  - [<span data-ttu-id="a12ae-112">Voraussetzungen für die Aktivierung der Kerberos-Authentifizierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a12ae-112">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [<span data-ttu-id="a12ae-113">Erstellen eines Kerberos-Authentifizierungs Kontos in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a12ae-113">Create a Kerberos authentication account in Lync Server 2013</span></span>](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [<span data-ttu-id="a12ae-114">Zuweisen eines Kerberos-Authentifizierungs Kontos zu einem Standort in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a12ae-114">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [<span data-ttu-id="a12ae-115">Einrichten von Kennwörtern für das Kerberos-Authentifizierungs Konto in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a12ae-115">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [<span data-ttu-id="a12ae-116">In lync Server 2013 hinzufügen der Kerberos-Authentifizierung zu anderen Websites</span><span class="sxs-lookup"><span data-stu-id="a12ae-116">In Lync Server 2013 add Kerberos authentication to other sites</span></span>](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [<span data-ttu-id="a12ae-117">In lync Server 2013 Entfernen der Kerberos-Authentifizierung von einer Website</span><span class="sxs-lookup"><span data-stu-id="a12ae-117">In Lync Server 2013 remove Kerberos authentication from a site</span></span>](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [<span data-ttu-id="a12ae-118">Testen und melden des Status und der Zuweisung der Kerberos-Authentifizierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a12ae-118">Testing and reporting the status and assignment of Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

