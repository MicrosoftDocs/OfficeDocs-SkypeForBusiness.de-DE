---
title: Skype-Raum System-Softwarelizenz für Skype for Business
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
description: Lesen Sie dieses Thema und erfahren Sie, wie Sie überprüfen, ob Sie über eine Volumenlizenzierung für die Skype for Business-Software verfügen.
ms.openlocfilehash: 5de1fc9204e22b30431f692770e3ec663599dd73
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768478"
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="b13c1-103">Skype Room System: Skype for Business-Softwarelizenz</span><span class="sxs-lookup"><span data-stu-id="b13c1-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="b13c1-104">Lesen Sie dieses Thema und erfahren Sie, wie Sie überprüfen, ob Sie über eine Volumenlizenzierung für die Skype for Business-Software verfügen.</span><span class="sxs-lookup"><span data-stu-id="b13c1-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="b13c1-105">Skype Room System verwendet einen installierten Skype for Business-Client, für den eine Software-Volumenlizenz erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b13c1-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="b13c1-106">Informieren Sie sich vor der Bereitstellung des ersten Skype-Raumsystems über den Volumenlizenz Status der Bereitstellung-mithilfe von Schlüsselverwaltungsservern (KMS) oder mehrerer Aktivierungsschlüssel (MAK).</span><span class="sxs-lookup"><span data-stu-id="b13c1-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="b13c1-107">Schlüsselverwaltungsserver (KMS)</span><span class="sxs-lookup"><span data-stu-id="b13c1-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="b13c1-108">Wenn KMS vorhanden ist und die Aktivierung von Skype for Business-Volumenlizenzen vertreibt, wird der Skype for Business-Client automatisch vom Skype-Raum System aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b13c1-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="b13c1-109">So finden Sie heraus, ob KMS vorhanden sind:</span><span class="sxs-lookup"><span data-stu-id="b13c1-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="b13c1-110">Führen Sie an einer Eingabeaufforderung Folgendes aus:`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="b13c1-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="b13c1-111">Weitere Informationen finden Sie unter [so wird es gemacht: Ermitteln von Office-und Windows KMS-Hosts über DNS und Entfernen nicht autorisierter Instanzen](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span><span class="sxs-lookup"><span data-stu-id="b13c1-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="b13c1-112">Informationen zum Einrichten eines KMS finden Sie unter [KMS-Aktivierung von Office 2013](https://technet.microsoft.com/library/ee624357.aspx) und [GVLKs für KMS und Active Directory-Aktivierung von Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span><span class="sxs-lookup"><span data-stu-id="b13c1-112">To set up a KMS, see [KMS activation of Office 2013](https://technet.microsoft.com/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span></span>
  
<span data-ttu-id="b13c1-113">Office 2013 Generic Volume License Key für lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (dieser Schlüssel bewirkt, dass das Skype-Raum System nach einem KMS im Netzwerk sucht).</span><span class="sxs-lookup"><span data-stu-id="b13c1-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="b13c1-114">Mehrfachaktivierungsschlüssel (MAK) aus dem Volume License Service Center (VLSC)</span><span class="sxs-lookup"><span data-stu-id="b13c1-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="b13c1-115">Wenn der Kunde eine andere Volumenlizenz Software verwendet, verwaltet die IT-Abteilung die Software Aktivierungen und den Volumenlizenz Vertrag (VLA) mit dem VLSC.</span><span class="sxs-lookup"><span data-stu-id="b13c1-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="b13c1-116">Auf diese Weise kann das Unternehmen auch Skype for Business-VL-Aktivierungen erwerben, nach denen das Unternehmen einen MAK für die Eingabe in die Skype Room-System Administratorkonsole erhalten kann.</span><span class="sxs-lookup"><span data-stu-id="b13c1-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="b13c1-117">Ein Kunde mit einem Vla muss seine VLSC-Anmeldeinformationen kennen, die verwendet werden, um den Vertrag zu verwalten und MAK zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b13c1-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="b13c1-118">Wenn Sie unsicher sind, sollte die Finanzabteilung des Kunden bestätigen können, ob der Kunde eine Vla bezahlt hat.</span><span class="sxs-lookup"><span data-stu-id="b13c1-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="b13c1-119">Greifen Sie, um einen MAK zu beziehen, auf das Volume Licensing Service Center zu, um die Vereinbarungen anzeigen zu lassen und um Produktschlüssel (MAK) herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="b13c1-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="b13c1-120">Weitere Informationen finden Sie im [Volumen Lizenzierungs-Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="b13c1-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-office-365-without-vlsc-access"></a><span data-ttu-id="b13c1-121">MAK für Office 365 ohne VLSC-Zugriff</span><span class="sxs-lookup"><span data-stu-id="b13c1-121">MAK for Office 365 without VLSC access</span></span>

<span data-ttu-id="b13c1-122">Wenn der Kunde keine VolumenLizenzvereinbarung hat, ist die Verwaltung von Skype for Business-Aktivierungen wesentlich schwieriger.</span><span class="sxs-lookup"><span data-stu-id="b13c1-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="b13c1-123">Office 365-Kunden ohne VLSC-Zugriff können jedoch ein Werbe-MAK erhalten, indem Sie dem OEM, der das Skype-Raum System verkauft, die folgenden Informationen zur Verfügung stellen:</span><span class="sxs-lookup"><span data-stu-id="b13c1-123">However, Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="b13c1-124">Name des Unternehmens</span><span class="sxs-lookup"><span data-stu-id="b13c1-124">Company name</span></span>
    
- <span data-ttu-id="b13c1-125">Name, E-Mail-Adresse und Telefonnummer des Kontakts für die Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="b13c1-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="b13c1-126">Anzahl der bereitgestellten Systeme</span><span class="sxs-lookup"><span data-stu-id="b13c1-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="b13c1-127">Bereitstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="b13c1-127">Deployment date</span></span>
    
- <span data-ttu-id="b13c1-128">Wenn der Kunde über einen Microsoft Technical Account Manager verfügt, Name und Kontaktinformationen des TAM</span><span class="sxs-lookup"><span data-stu-id="b13c1-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
    

