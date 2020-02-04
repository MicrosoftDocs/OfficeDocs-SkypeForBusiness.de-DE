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
ms.openlocfilehash: 8c644dd613b3186b314e8fc78b42197709286200
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="f7f93-102">Einrichten der Kerberos-Authentifizierung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7f93-102">Setting up Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7f93-103">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f7f93-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f7f93-104">Lync Server 2013 unterstützt die NTLM-und Kerberos-Authentifizierung für Webdienste.</span><span class="sxs-lookup"><span data-stu-id="f7f93-104">Lync Server 2013 supports NTLM and Kerberos authentication for Web Services.</span></span> <span data-ttu-id="f7f93-105">Office Communications Server 2007 und Office Communications Server 2007 R2 verwendeten die standardmäßigen RTCComponentService und RTCService als Benutzerkonten, um die Webdienste-Anwendungspools auszuführen, sodass dem Benutzer ein Dienstprinzipalname (SPN) zugewiesen werden konnte. Konten und als Authentifizierungs Prinzipal fungieren.</span><span class="sxs-lookup"><span data-stu-id="f7f93-105">Office Communications Server 2007 and Office Communications Server 2007 R2 used the default RTCComponentService and RTCService as the user accounts to run the Web Services application pools, allowing for a service principal name (SPN) to be assigned to the user accounts and to act as the authentication principal.</span></span> <span data-ttu-id="f7f93-106">Lync Server verwendet Network Service zum Ausführen von Webdiensten, und Network Services kann keine SPNs zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="f7f93-106">Lync Server uses NetworkService to run Web Services and NetworkService cannot have SPNs assigned to it.</span></span>

<span data-ttu-id="f7f93-107">Um das Problem zu lösen, dass keine Active Directory-Objekte für die SPNs enthalten sind, kann die lync Server-Systemsteuerung Computerkontoobjekte zu diesem Zweck verwenden.</span><span class="sxs-lookup"><span data-stu-id="f7f93-107">To solve the issue of not having Active Directory objects to hold the SPNs, Lync Server Control Panel can use computer account objects for this purpose.</span></span> <span data-ttu-id="f7f93-108">Die Computerkontoobjekte können die SPNs enthalten und unterliegen nicht dem Ablauf von Kennwörtern, was ein Problem bei der Verwendung von Benutzerkonten in früheren Versionen war.</span><span class="sxs-lookup"><span data-stu-id="f7f93-108">The computer account objects can hold the SPNs and are not subject to password expiration, which was an issue with using user accounts in previous versions.</span></span>

<span data-ttu-id="f7f93-109">Sie verwenden Windows PowerShell-Cmdlets, um die Computerobjekte so zu konfigurieren, dass die Kerberos-Authentifizierung bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f7f93-109">You use Windows PowerShell cmdlets to configure the computer objects to provide Kerberos authentication.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f7f93-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f7f93-110">In This Section</span></span>

  - [<span data-ttu-id="f7f93-111">Voraussetzungen zur Aktivierung der Kerberos-Authentifizierung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7f93-111">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [<span data-ttu-id="f7f93-112">Erstellen eines Kerberos-Authentifizierungskontos in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7f93-112">Create a Kerberos authentication account in Lync Server 2013</span></span>](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [<span data-ttu-id="f7f93-113">Zuweisen eines Kerberos-Authentifizierungskontos zu einem Standort in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7f93-113">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [<span data-ttu-id="f7f93-114">Einrichten von Kennwörtern für ein Kerberos-Authentifizierungskonto in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7f93-114">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [<span data-ttu-id="f7f93-115">Hinzufügen der Kerberos-Authentifizierung zu weiteren Standorten in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7f93-115">In Lync Server 2013 add Kerberos authentication to other sites</span></span>](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [<span data-ttu-id="f7f93-116">Entfernen der Kerberos-Authentifizierung aus einem Standort in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7f93-116">In Lync Server 2013 remove Kerberos authentication from a site</span></span>](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [<span data-ttu-id="f7f93-117">Test und Berichterstellung zu Status und Zuweisung der Kerberos-Authentifizierung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7f93-117">Testing and reporting the status and assignment of Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

