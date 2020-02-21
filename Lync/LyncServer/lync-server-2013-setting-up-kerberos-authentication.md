---
title: 'Lync Server 2013: Einrichten der Kerberos-Authentifizierung'
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
ms.openlocfilehash: 42f2c781b01aaa1ac00793f97067f24233c1e8db
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200561"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="f68f5-102">Einrichten der Kerberos-Authentifizierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f68f5-102">Setting up Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f68f5-103">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f68f5-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f68f5-104">Lync Server 2013 unterstützt NTLM-und Kerberos-Authentifizierung für Webdienste.</span><span class="sxs-lookup"><span data-stu-id="f68f5-104">Lync Server 2013 supports NTLM and Kerberos authentication for Web Services.</span></span> <span data-ttu-id="f68f5-105">Office Communications Server 2007 und Office Communications Server 2007 R2 verwendet die standardmäßigen RTCComponentService und RTCService als Benutzerkonten zum Ausführen der Webdienste Anwendungspools, sodass ein Dienstprinzipalname (Service Principal Name, SPN) dem Benutzer zugewiesen werden kann. Konten und als Authentifizierungs Prinzipal fungieren.</span><span class="sxs-lookup"><span data-stu-id="f68f5-105">Office Communications Server 2007 and Office Communications Server 2007 R2 used the default RTCComponentService and RTCService as the user accounts to run the Web Services application pools, allowing for a service principal name (SPN) to be assigned to the user accounts and to act as the authentication principal.</span></span> <span data-ttu-id="f68f5-106">Lync Server verwendet Network Service zum Ausführen von Webdienste, und Network Service kann keine SPNs zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="f68f5-106">Lync Server uses NetworkService to run Web Services and NetworkService cannot have SPNs assigned to it.</span></span>

<span data-ttu-id="f68f5-107">Um das Problem zu beheben, dass keine Active Directory-Objekte zum Speichern der SPNs zur Verfügung stehen, können lync Server-Systemsteuerung Computerkonto-Objekte zu diesem Zweck verwenden.</span><span class="sxs-lookup"><span data-stu-id="f68f5-107">To solve the issue of not having Active Directory objects to hold the SPNs, Lync Server Control Panel can use computer account objects for this purpose.</span></span> <span data-ttu-id="f68f5-108">Die Computerkontoobjekte können die Dienstprinzipalnamen enthalten und unterliegen keinem Kennwortablauf, was bei der Verwendung von Benutzerkonten in früheren Versionen ein Problem darstellte.</span><span class="sxs-lookup"><span data-stu-id="f68f5-108">The computer account objects can hold the SPNs and are not subject to password expiration, which was an issue with using user accounts in previous versions.</span></span>

<span data-ttu-id="f68f5-109">Verwenden Sie Windows PowerShell-Cmdlets, um die Computerobjekte für die Bereitstellung der Kerberos-Authentifizierung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f68f5-109">You use Windows PowerShell cmdlets to configure the computer objects to provide Kerberos authentication.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f68f5-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f68f5-110">In This Section</span></span>

  - [<span data-ttu-id="f68f5-111">Voraussetzungen für die Aktivierung der Kerberos-Authentifizierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f68f5-111">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [<span data-ttu-id="f68f5-112">Erstellen eines Kerberos-Authentifizierungs Kontos in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f68f5-112">Create a Kerberos authentication account in Lync Server 2013</span></span>](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [<span data-ttu-id="f68f5-113">Zuweisen eines Kerberos-Authentifizierungs Kontos zu einem Standort in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f68f5-113">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [<span data-ttu-id="f68f5-114">Einrichten von Kennwörtern für das Kerberos-Authentifizierungs Konto in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f68f5-114">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [<span data-ttu-id="f68f5-115">In lync Server 2013 hinzufügen der Kerberos-Authentifizierung zu anderen Websites</span><span class="sxs-lookup"><span data-stu-id="f68f5-115">In Lync Server 2013 add Kerberos authentication to other sites</span></span>](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [<span data-ttu-id="f68f5-116">In lync Server 2013 Entfernen der Kerberos-Authentifizierung von einer Website</span><span class="sxs-lookup"><span data-stu-id="f68f5-116">In Lync Server 2013 remove Kerberos authentication from a site</span></span>](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [<span data-ttu-id="f68f5-117">Testen und melden des Status und der Zuweisung der Kerberos-Authentifizierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f68f5-117">Testing and reporting the status and assignment of Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

