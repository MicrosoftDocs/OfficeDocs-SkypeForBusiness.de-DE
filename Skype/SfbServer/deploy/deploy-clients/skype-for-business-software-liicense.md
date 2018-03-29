---
title: Skype Raum System Skype für Business-Lizenz
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Lesen Sie dieses Thema und erfahren Sie, wie Sie überprüfen, ob Sie über eine Volumenlizenzierung für die Skype for Business-Software verfügen.
ms.openlocfilehash: e91a009c29647031d91e791ba5fd41ccc4578d1e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="19b9b-103">Skype Room System: Skype for Business-Softwarelizenz</span><span class="sxs-lookup"><span data-stu-id="19b9b-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="19b9b-104">Lesen Sie dieses Thema und erfahren Sie, wie Sie überprüfen, ob Sie über eine Volumenlizenzierung für die Skype for Business-Software verfügen.</span><span class="sxs-lookup"><span data-stu-id="19b9b-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="19b9b-105">Skype Raum System verwendet eine installierte Skype für Business-Client, die eine Volumenlizenz Software erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="19b9b-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="19b9b-106">Erfahren Sie vor der Bereitstellung von der ersten Skype Raum System, das Volume Lizenzstatus der Bereitstellung - Key Management Server (KMS) oder Mehrfachaktivierungsschlüssel (Multiple Activation Schlüssel, MAK) verwenden.</span><span class="sxs-lookup"><span data-stu-id="19b9b-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="19b9b-107">Schlüsselverwaltungsserver (KMS)</span><span class="sxs-lookup"><span data-stu-id="19b9b-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="19b9b-108">Wenn KMS vorhanden sind und Skype für Business Volume License Aktivierungen verteilt, wird das Skype Raum System automatisch die Skype für Business-Client aktiviert.</span><span class="sxs-lookup"><span data-stu-id="19b9b-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="19b9b-109">So finden Sie heraus, ob KMS vorhanden sind:</span><span class="sxs-lookup"><span data-stu-id="19b9b-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="19b9b-110">Führen Sie an der Eingabeaufforderung aus:`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="19b9b-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="19b9b-111">Weitere Informationen finden Sie unter [Office und Windows-KMS-Hosts über DNS-Ermittlung und Entfernen von nicht autorisierten Instanzen](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span><span class="sxs-lookup"><span data-stu-id="19b9b-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="19b9b-112">Informationen zum Einrichten eines KMS finden Sie unter [KMS-Aktivierung von Office 2013](https://technet.microsoft.com/en-us/library/ee624357.aspx) und [GVLKs für die KMS- und Active Directory-Aktivierung von Office 2013](https://technet.microsoft.com/en-us/library/dn385360.aspx)</span><span class="sxs-lookup"><span data-stu-id="19b9b-112">To set up a KMS, see [KMS activation of Office 2013](https://technet.microsoft.com/en-us/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/en-us/library/dn385360.aspx)</span></span>
  
<span data-ttu-id="19b9b-113">Office 2013 Generic Volume License Product Key für Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (dieser Schlüssel wird das Skype Raum System für ein KMS im Netzwerk zu suchen.)</span><span class="sxs-lookup"><span data-stu-id="19b9b-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="19b9b-114">Mehrfachaktivierungsschlüssel (MAK) aus dem Volume License Service Center (VLSC)</span><span class="sxs-lookup"><span data-stu-id="19b9b-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="19b9b-115">Wenn der Kunde anderen Volume License Software verwendet wird, wird die IT-Abteilung die Software Aktivierungen und Volume License Vereinbarung (VLA) mit der VLSC verwalten.</span><span class="sxs-lookup"><span data-stu-id="19b9b-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="19b9b-116">Dadurch können auch das Unternehmen Skype für Business VL-Aktivierungen erwerben nach dem das Unternehmen einen MAK für die Eingabe in der Verwaltungskonsole von Skype Raum System erhalten kann.</span><span class="sxs-lookup"><span data-stu-id="19b9b-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="19b9b-117">Ein Kunde mit einer VLA muss ihre Anmeldeinformationen VLSC wissen, welche die zum Verwalten der Vereinbarung und Abrufen von MAK verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="19b9b-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="19b9b-118">Wenn Sie nicht sicher sind, sollte der Kunde Finanzabteilung können Sie überprüfen, wenn der Kunde einen VLA gezahlt haben.</span><span class="sxs-lookup"><span data-stu-id="19b9b-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="19b9b-119">Greifen Sie, um einen MAK zu beziehen, auf das Volume Licensing Service Center zu, um die Vereinbarungen anzeigen zu lassen und um Produktschlüssel (MAK) herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="19b9b-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="19b9b-120">Weitere Informationen finden Sie im [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="19b9b-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-office-365-without-vlsc-access"></a><span data-ttu-id="19b9b-121">MAK für Office 365 ohne VLSC-Zugriff</span><span class="sxs-lookup"><span data-stu-id="19b9b-121">MAK for Office 365 without VLSC access</span></span>

<span data-ttu-id="19b9b-122">Wenn der Kunde einen Volumenlizenzvertrag besitzt, können Skype für Business Aktivierungen schwieriger zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="19b9b-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="19b9b-123">Jedoch können Office 365-Kunden ohne VLSC Zugriff einen Werbe MAK anfordern, indem er die folgende Informationen an dem OEM verkaufen Skype Raum System:</span><span class="sxs-lookup"><span data-stu-id="19b9b-123">However, Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="19b9b-124">Name des Unternehmens</span><span class="sxs-lookup"><span data-stu-id="19b9b-124">Company name</span></span>
    
- <span data-ttu-id="19b9b-125">Name, E-Mail-Adresse und Telefonnummer des Kontakts für die Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="19b9b-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="19b9b-126">Anzahl der Systeme bereitgestellt</span><span class="sxs-lookup"><span data-stu-id="19b9b-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="19b9b-127">Bereitstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="19b9b-127">Deployment date</span></span>
    
- <span data-ttu-id="19b9b-128">Wenn der Kunde einen Microsoft Technical Account Manager, des TAM Namen und Kontaktinformationen</span><span class="sxs-lookup"><span data-stu-id="19b9b-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
    

