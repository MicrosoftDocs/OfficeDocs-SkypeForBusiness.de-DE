---
title: 'Lync Server 2013: Konfigurieren der Unternehmenszertifizierungsstelle für die Smartcard-Authentifizierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise CA for smart card authentication
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308571(v=OCS.15)
ms:contentKeyID: 54973692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44df62031e679c641b4c7dbe6b5c205e1ae899e8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728965"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="c0dc9-102">Konfigurieren der Unternehmenszertifizierungsstelle für die Smartcard-Authentifizierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0dc9-102">Configuring Enterprise CA for smart card authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0dc9-103">_**Letztes Änderungsdatum des Themas:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="c0dc9-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="c0dc9-104">Im folgenden Abschnitt wird beschrieben, wie Sie eine Unternehmensstammzertifizierungsstelle konfigurieren, um die Smartcard-Authentifizierung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c0dc9-104">The following section describes how to configure an Enterprise Root Certification Authority (CA) to support smart card authentication.</span></span> <span data-ttu-id="c0dc9-105">Informationen zum Installieren einer Unternehmensstammzertifizierungsstelle finden Sie unter Installieren einer Unternehmensstammzertifizierungsstelle [http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364)unter.</span><span class="sxs-lookup"><span data-stu-id="c0dc9-105">For information on how to install an Enterprise Root CA, see Install an Enterprise Root Certification Authority at [http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364).</span></span>

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="c0dc9-106">Konfigurieren einer Unternehmensstammzertifizierungsstelle zur Unterstützung der Smartcard-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="c0dc9-106">Configuring an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="c0dc9-107">In den folgenden Schritten wird das Konfigurieren einer Stammzertifizierungsstelle im Unternehmen zur Unterstützung der SmartCard-Authentifizierung beschrieben:</span><span class="sxs-lookup"><span data-stu-id="c0dc9-107">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

1.  <span data-ttu-id="c0dc9-108">Melden Sie sich beim CA-Computer des Unternehmens mit dem Konto eines Domänenadministrators an.</span><span class="sxs-lookup"><span data-stu-id="c0dc9-108">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="c0dc9-109">Starten Sie den System-Manager und überprüfen Sie, ob die Zertifizierungsstellen-Webregistrierungsrolle installiert ist.</span><span class="sxs-lookup"><span data-stu-id="c0dc9-109">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3.  <span data-ttu-id="c0dc9-110">Öffnen Sie im Menü **Verwaltungstools** die Verwaltungskonsole **Zertifizierungsstelle**.</span><span class="sxs-lookup"><span data-stu-id="c0dc9-110">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4.  <span data-ttu-id="c0dc9-111">Erweitern Sie im Navigationsbereich den Knoten **Zertifizierungsstelle**.</span><span class="sxs-lookup"><span data-stu-id="c0dc9-111">In the Navigation pane, expand **Certification Authority**.</span></span>

5.  <span data-ttu-id="c0dc9-112">Klicken Sie mit der rechten Maustaste auf **Zertifikatvorlagen**, wählen Sie **Neu** und anschließend **Auszustellende Zertifikatvorlage** aus.</span><span class="sxs-lookup"><span data-stu-id="c0dc9-112">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6.  <span data-ttu-id="c0dc9-113">Wählen Sie **Enrollment Agent**, **SmartCard-Benutzer** und **SmartCard-Anmeldung** aus.</span><span class="sxs-lookup"><span data-stu-id="c0dc9-113">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7.  <span data-ttu-id="c0dc9-114">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0dc9-114">Click **OK**.</span></span>

8.  <span data-ttu-id="c0dc9-115">Klicken Sie mit der rechten Maustaste auf **Zertifikatvorlagen**.</span><span class="sxs-lookup"><span data-stu-id="c0dc9-115">Right click on **Certificate Templates**.</span></span>

9.  <span data-ttu-id="c0dc9-116">Wählen Sie **Verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="c0dc9-116">Select **Manage**.</span></span>

10. <span data-ttu-id="c0dc9-117">Öffnen Sie die Eigenschaften der Vorlage „SmartCard-Benutzer“.</span><span class="sxs-lookup"><span data-stu-id="c0dc9-117">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="c0dc9-118">Klicken Sie auf die Registerkarte **Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="c0dc9-118">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="c0dc9-119">Ändern Sie die Berechtigungen wie folgt:</span><span class="sxs-lookup"><span data-stu-id="c0dc9-119">Change the permissions as follows:</span></span>
    
      - <span data-ttu-id="c0dc9-120">Fügen Sie einzelne AD-Konten mit den Berechtigungen „Lesen/Registrieren (Zulassen)“ hinzu, oder</span><span class="sxs-lookup"><span data-stu-id="c0dc9-120">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="c0dc9-121">Fügen Sie eine Sicherheitsgruppe hinzu, die SmartCard-Benutzer mit den Berechtigungen „Lesen/Registrieren (Zulassen)“ enthält, hinzu, oder</span><span class="sxs-lookup"><span data-stu-id="c0dc9-121">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="c0dc9-122">Fügen Sie die Gruppe „Domänenbenutzer“ mit den Berechtigungen „Lesen/Registrieren (Zulassen“) hinzu</span><span class="sxs-lookup"><span data-stu-id="c0dc9-122">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

