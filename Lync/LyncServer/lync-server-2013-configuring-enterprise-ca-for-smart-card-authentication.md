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
ms.openlocfilehash: 315d98e26b471e2d9dd84dcb70cd7302e924e9b3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="86f35-102">Konfigurieren der Unternehmenszertifizierungsstelle für die Smartcard-Authentifizierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86f35-102">Configuring Enterprise CA for smart card authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86f35-103">_**Letztes Änderungsstand des Themas:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="86f35-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="86f35-104">Im folgenden Abschnitt wird beschrieben, wie Sie eine Unternehmensstammzertifizierungsstelle (Certification Authority, ca) zur Unterstützung der Smartcard-Authentifizierung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="86f35-104">The following section describes how to configure an Enterprise Root Certification Authority (CA) to support smart card authentication.</span></span> <span data-ttu-id="86f35-105">Informationen zum Installieren einer Stammzertifizierungsstelle für Unternehmen finden Sie unter Installieren einer Stamm Zertifizierungs [https://go.microsoft.com/fwlink/p/?LinkID=313364](https://go.microsoft.com/fwlink/p/?linkid=313364)Stelle für Unternehmen unter.</span><span class="sxs-lookup"><span data-stu-id="86f35-105">For information on how to install an Enterprise Root CA, see Install an Enterprise Root Certification Authority at [https://go.microsoft.com/fwlink/p/?LinkID=313364](https://go.microsoft.com/fwlink/p/?linkid=313364).</span></span>

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="86f35-106">Konfigurieren einer Stammzertifizierungsstelle für Unternehmen zur Unterstützung der Smartcard-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="86f35-106">Configuring an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="86f35-107">In den folgenden Schritten wird das Konfigurieren einer Stammzertifizierungsstelle für Unternehmen zur Unterstützung der Smartcard-Authentifizierung beschrieben:</span><span class="sxs-lookup"><span data-stu-id="86f35-107">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

1.  <span data-ttu-id="86f35-108">Melden Sie sich mit einem Domänenadministratorkonto beim Enterprise-Zertifizierungsstellencomputer an.</span><span class="sxs-lookup"><span data-stu-id="86f35-108">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="86f35-109">Starten Sie System-Manager, und stellen Sie sicher, dass die Webregistrierungs Rolle der Zertifizierungsstelle installiert ist.</span><span class="sxs-lookup"><span data-stu-id="86f35-109">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3.  <span data-ttu-id="86f35-110">Öffnen Sie im Menü **Verwaltungs Tools** die Verwaltungskonsole der **Zertifizierungsstelle** .</span><span class="sxs-lookup"><span data-stu-id="86f35-110">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4.  <span data-ttu-id="86f35-111">Erweitern Sie im Navigationsbereich die Option **Zertifizierungsstelle**.</span><span class="sxs-lookup"><span data-stu-id="86f35-111">In the Navigation pane, expand **Certification Authority**.</span></span>

5.  <span data-ttu-id="86f35-112">Klicken Sie mit der rechten Maustaste auf **Zertifikatvorlagen**, wählen Sie **neu**, und wählen Sie dann **Auszustellende Zertifikatvorlage**aus.</span><span class="sxs-lookup"><span data-stu-id="86f35-112">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6.  <span data-ttu-id="86f35-113">Wählen Sie **Registrierungs-Agent**, Smartcard- **Benutzer**und Smartcard- **Anmeldung**aus.</span><span class="sxs-lookup"><span data-stu-id="86f35-113">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7.  <span data-ttu-id="86f35-114">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="86f35-114">Click **OK**.</span></span>

8.  <span data-ttu-id="86f35-115">Klicken Sie mit der rechten Maustaste auf **Zertifikatvorlagen**.</span><span class="sxs-lookup"><span data-stu-id="86f35-115">Right click on **Certificate Templates**.</span></span>

9.  <span data-ttu-id="86f35-116">Wählen Sie **Manage**aus.</span><span class="sxs-lookup"><span data-stu-id="86f35-116">Select **Manage**.</span></span>

10. <span data-ttu-id="86f35-117">Öffnen Sie die Eigenschaften der Smartcard-Benutzervorlage.</span><span class="sxs-lookup"><span data-stu-id="86f35-117">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="86f35-118">Klicken Sie auf die Registerkarte **Sicherheit** .</span><span class="sxs-lookup"><span data-stu-id="86f35-118">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="86f35-119">Ändern Sie die Berechtigungen wie folgt:</span><span class="sxs-lookup"><span data-stu-id="86f35-119">Change the permissions as follows:</span></span>
    
      - <span data-ttu-id="86f35-120">Hinzufügen einzelner Benutzer Ad-Konten mit Berechtigungen zum Lesen/registrieren (zulassen) oder</span><span class="sxs-lookup"><span data-stu-id="86f35-120">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="86f35-121">Hinzufügen einer Sicherheitsgruppe, die Smartcard-Benutzer mit Berechtigungen zum Lesen/registrieren (zulassen) enthält, oder</span><span class="sxs-lookup"><span data-stu-id="86f35-121">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="86f35-122">Hinzufügen der Gruppe "Domänenbenutzer" mit Berechtigungen zum Lesen/registrieren (zulassen)</span><span class="sxs-lookup"><span data-stu-id="86f35-122">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

