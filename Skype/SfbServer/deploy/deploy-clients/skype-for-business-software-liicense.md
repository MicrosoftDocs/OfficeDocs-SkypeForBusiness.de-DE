---
title: Skype Room System Skype for Business-Softwarelizenz
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Lesen Sie dieses Thema, um zu erfahren, wie Sie überprüfen können, ob Sie über eine Skype for Business Software Volumenlizenz verfügen.
ms.openlocfilehash: a44e95d8cd488e2b12e03ee9848ef3d1b254180c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220925"
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="01cc7-103">Skype Room System: Skype for Business Softwarelizenz</span><span class="sxs-lookup"><span data-stu-id="01cc7-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="01cc7-104">Lesen Sie dieses Thema, um zu erfahren, wie Sie überprüfen können, ob Sie über eine Skype for Business Software Volumenlizenz verfügen.</span><span class="sxs-lookup"><span data-stu-id="01cc7-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="01cc7-105">Skype Room System verwendet einen installierten Skype for Business-Client, für den eine Software Volumenlizenz erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="01cc7-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="01cc7-106">Ermitteln Sie vor dem Bereitstellen des ersten Skype-Raumsystems den Volumenlizenz Status der Bereitstellung mithilfe von Schlüsselverwaltungsservern (KMS) oder mehrfachaktivierungsschlüsseln (MAK).</span><span class="sxs-lookup"><span data-stu-id="01cc7-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="01cc7-107">Schlüsselverwaltungsserver (KMS)</span><span class="sxs-lookup"><span data-stu-id="01cc7-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="01cc7-108">Wenn KMS vorhanden ist und Skype for Business Volumenlizenz Aktivierungen verteilen wird, aktiviert das Skype Room-System automatisch den Skype for Business-Client.</span><span class="sxs-lookup"><span data-stu-id="01cc7-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="01cc7-109">So ermitteln Sie, ob KMS vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="01cc7-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="01cc7-110">Führen Sie an einer Eingabeaufforderung Folgendes aus:`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="01cc7-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="01cc7-111">Weitere Informationen finden Sie unter [So ermitteln Sie Office-und Windows KMS-Hosts über DNS und Entfernen nicht autorisierter Instanzen](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span><span class="sxs-lookup"><span data-stu-id="01cc7-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="01cc7-112">Informationen zum Einrichten eines KMS finden Sie unter [KMS-Aktivierung von Office 2013](https://technet.microsoft.com/library/ee624357.aspx) und [GVLKs für KMS und Active Directory Aktivierung von Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span><span class="sxs-lookup"><span data-stu-id="01cc7-112">To set up a KMS, see [KMS activation of Office 2013](https://technet.microsoft.com/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span></span>
  
<span data-ttu-id="01cc7-113">Office 2013 generischer Volumenlizenzschlüssel für lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (dieser Schlüssel veranlasst das Skype Room-System, nach einem KMS im Netzwerk zu suchen.)</span><span class="sxs-lookup"><span data-stu-id="01cc7-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="01cc7-114">Mehrfachaktivierungsschlüssel (MAK) aus dem Volume License Service Center (VLSC)</span><span class="sxs-lookup"><span data-stu-id="01cc7-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="01cc7-115">Wenn der Kunde eine andere Volumenlizenz Software verwendet, verwaltet die IT-Abteilung die Software Aktivierungen und den Volumenlizenz Vertrag (VLA) mithilfe der VLSC.</span><span class="sxs-lookup"><span data-stu-id="01cc7-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="01cc7-116">Dadurch kann das Unternehmen auch Skype for Business VL-Aktivierungen erwerben, nach denen das Unternehmen einen MAK für die Eingabe in der Skype Room System-Verwaltungskonsole erhalten kann.</span><span class="sxs-lookup"><span data-stu-id="01cc7-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="01cc7-117">Ein Kunde mit Vla muss seine VLSC-Anmeldeinformationen kennen, die zur Verwaltung der Vereinbarung und zum Abrufen von MAK verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="01cc7-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="01cc7-118">Wenn die Finanzabteilung des Kunden unsicher ist, sollte Sie bestätigen können, wenn der Kunde eine Vla bezahlt hat.</span><span class="sxs-lookup"><span data-stu-id="01cc7-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="01cc7-119">Um einen MAK zu erhalten, greifen Sie auf das Volumen Lizenzierungs-Service Center zu, um Vereinbarungen anzuzeigen und Produktschlüssel (MAK) herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="01cc7-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="01cc7-120">Weitere Informationen finden Sie im [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="01cc7-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a><span data-ttu-id="01cc7-121">MAK für Microsoft 365 oder Office 365 ohne VLSC-Zugriff</span><span class="sxs-lookup"><span data-stu-id="01cc7-121">MAK for Microsoft 365 or Office 365 without VLSC access</span></span>

<span data-ttu-id="01cc7-122">Wenn der Kunde nicht über eine Volumenlizenzvereinbarung verfügt, ist die Verwaltung Skype for Business Aktivierungen wesentlich schwieriger.</span><span class="sxs-lookup"><span data-stu-id="01cc7-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="01cc7-123">Microsoft 365 und Office 365 Kunden ohne VLSC-Zugriff können jedoch einen Promotions-MAK erhalten, indem Sie den OEM, der das Skype Room-System verkauft, folgende Informationen bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="01cc7-123">However, Microsoft 365 and Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="01cc7-124">Firma</span><span class="sxs-lookup"><span data-stu-id="01cc7-124">Company name</span></span>
    
- <span data-ttu-id="01cc7-125">Bereitstellungs Kontakt Name, e-Mail und Telefonnummer</span><span class="sxs-lookup"><span data-stu-id="01cc7-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="01cc7-126">Anzahl der bereitgestellten Systeme</span><span class="sxs-lookup"><span data-stu-id="01cc7-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="01cc7-127">Bereitstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="01cc7-127">Deployment date</span></span>
    
- <span data-ttu-id="01cc7-128">Wenn der Kunde über einen technischen Microsoft Account Manager verfügt, werden der Name und die Kontaktinformationen des TAM</span><span class="sxs-lookup"><span data-stu-id="01cc7-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
    

