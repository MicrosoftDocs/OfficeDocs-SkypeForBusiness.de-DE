---
title: 'Lync Server 2013: Konfigurieren der Unternehmenszertifizierungsstelle für die Smartcard-Authentifizierung'
description: 'Lync Server 2013: Konfigurieren der Unternehmenszertifizierungsstelle für die Smartcard-Authentifizierung.'
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
ms.openlocfilehash: 98044c96dd04d02fd87609918f309cf65227b133
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548441"
---
# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="21240-103">Konfigurieren der Unternehmenszertifizierungsstelle für die Smartcard-Authentifizierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21240-103">Configuring Enterprise CA for smart card authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21240-104">_**Letztes Änderungsstand des Themas:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="21240-104">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="21240-105">Im folgenden Abschnitt wird beschrieben, wie Sie eine Unternehmensstammzertifizierungsstelle (Certification Authority, ca) zur Unterstützung der Smartcard-Authentifizierung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="21240-105">The following section describes how to configure an Enterprise Root Certification Authority (CA) to support smart card authentication.</span></span> <span data-ttu-id="21240-106">Informationen zum Installieren einer Stammzertifizierungsstelle für Unternehmen finden Sie unter Installieren einer Stammzertifizierungsstelle für Unternehmen unter [https://go.microsoft.com/fwlink/p/?LinkID=313364](https://go.microsoft.com/fwlink/p/?linkid=313364) .</span><span class="sxs-lookup"><span data-stu-id="21240-106">For information on how to install an Enterprise Root CA, see Install an Enterprise Root Certification Authority at [https://go.microsoft.com/fwlink/p/?LinkID=313364](https://go.microsoft.com/fwlink/p/?linkid=313364).</span></span>

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="21240-107">Konfigurieren einer Stammzertifizierungsstelle für Unternehmen zur Unterstützung der Smartcard-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="21240-107">Configuring an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="21240-108">In den folgenden Schritten wird das Konfigurieren einer Stammzertifizierungsstelle für Unternehmen zur Unterstützung der Smartcard-Authentifizierung beschrieben:</span><span class="sxs-lookup"><span data-stu-id="21240-108">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

1.  <span data-ttu-id="21240-109">Melden Sie sich mit einem Domänenadministratorkonto beim Enterprise-Zertifizierungsstellencomputer an.</span><span class="sxs-lookup"><span data-stu-id="21240-109">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="21240-110">Starten Sie System-Manager, und stellen Sie sicher, dass die Webregistrierungs Rolle der Zertifizierungsstelle installiert ist.</span><span class="sxs-lookup"><span data-stu-id="21240-110">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3.  <span data-ttu-id="21240-111">Öffnen Sie im Menü **Verwaltungs Tools** die Verwaltungskonsole der **Zertifizierungsstelle** .</span><span class="sxs-lookup"><span data-stu-id="21240-111">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4.  <span data-ttu-id="21240-112">Erweitern Sie im Navigationsbereich die Option **Zertifizierungsstelle**.</span><span class="sxs-lookup"><span data-stu-id="21240-112">In the Navigation pane, expand **Certification Authority**.</span></span>

5.  <span data-ttu-id="21240-113">Klicken Sie mit der rechten Maustaste auf **Zertifikatvorlagen**, wählen Sie **neu**, und wählen Sie dann **Auszustellende Zertifikatvorlage**aus.</span><span class="sxs-lookup"><span data-stu-id="21240-113">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6.  <span data-ttu-id="21240-114">Wählen Sie **Registrierungs-Agent**, Smartcard- **Benutzer**und Smartcard- **Anmeldung**aus.</span><span class="sxs-lookup"><span data-stu-id="21240-114">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7.  <span data-ttu-id="21240-115">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="21240-115">Click **OK**.</span></span>

8.  <span data-ttu-id="21240-116">Klicken Sie mit der rechten Maustaste auf **Zertifikatvorlagen**.</span><span class="sxs-lookup"><span data-stu-id="21240-116">Right click on **Certificate Templates**.</span></span>

9.  <span data-ttu-id="21240-117">Wählen Sie **Manage**aus.</span><span class="sxs-lookup"><span data-stu-id="21240-117">Select **Manage**.</span></span>

10. <span data-ttu-id="21240-118">Öffnen Sie die Eigenschaften der Smartcard-Benutzervorlage.</span><span class="sxs-lookup"><span data-stu-id="21240-118">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="21240-119">Klicken Sie auf die Registerkarte **Sicherheit** .</span><span class="sxs-lookup"><span data-stu-id="21240-119">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="21240-120">Ändern Sie die Berechtigungen wie folgt:</span><span class="sxs-lookup"><span data-stu-id="21240-120">Change the permissions as follows:</span></span>
    
      - <span data-ttu-id="21240-121">Hinzufügen einzelner Benutzer Ad-Konten mit Berechtigungen zum Lesen/registrieren (zulassen) oder</span><span class="sxs-lookup"><span data-stu-id="21240-121">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="21240-122">Hinzufügen einer Sicherheitsgruppe, die Smartcard-Benutzer mit Berechtigungen zum Lesen/registrieren (zulassen) enthält, oder</span><span class="sxs-lookup"><span data-stu-id="21240-122">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="21240-123">Hinzufügen der Gruppe "Domänenbenutzer" mit Berechtigungen zum Lesen/registrieren (zulassen)</span><span class="sxs-lookup"><span data-stu-id="21240-123">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

