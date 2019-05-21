---
title: Set-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: Das Cmdlet „Set-CcExternalCertificateFilePath“ gibt den Pfad an, in dem das Zertifikat für den Vermittlungsserver oder den Edgeserver gespeichert ist.
ms.openlocfilehash: bc22771c20277d9de99660551864d600f06b3acc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286985"
---
# <a name="set-ccexternalcertificatefilepath"></a><span data-ttu-id="3c2fa-103">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="3c2fa-103">Set-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="3c2fa-104">Das Cmdlet „Set-CcExternalCertificateFilePath“ gibt den Pfad an, in dem das Zertifikat für den Vermittlungsserver oder den Edgeserver gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="3c2fa-104">The Set-CcExternalCertificateFilePath cmdlet specifies the path where the certificate for the Mediation Server or Edge Server is stored.</span></span>
  
<span data-ttu-id="3c2fa-p101">Dieses Zertifikat ist während der Bereitstellung oder beim Hinzufügen neuer Appliances von Skype for Business Cloud Connector Edition erforderlich. Mit diesem Befehl können Sie auch nach der Bereitstellung ein neues Zertifikat für den Vermittlungsserver importieren.</span><span class="sxs-lookup"><span data-stu-id="3c2fa-p101">This certificate is required during deployment or when adding new appliances of Skype for Business Cloud Connector Edition. The command also allows importing a new certificate for the Mediation Server after the deployment.</span></span>
  
<span data-ttu-id="3c2fa-107">Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1 und 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="3c2fa-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="3c2fa-108">Beispiele</span><span class="sxs-lookup"><span data-stu-id="3c2fa-108">Examples</span></span>
<span data-ttu-id="3c2fa-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3c2fa-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="3c2fa-110">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="3c2fa-110">Example 1</span></span>

<span data-ttu-id="3c2fa-111">Im folgenden Beispiel wird der Pfad des Zertifikats für den Edgeserver festgelegt:</span><span class="sxs-lookup"><span data-stu-id="3c2fa-111">The following example sets the path of the certificate for the Edge Server:</span></span>
  
```
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a><span data-ttu-id="3c2fa-112">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="3c2fa-112">Example 2</span></span>

<span data-ttu-id="3c2fa-113">Im nächsten Beispiel wird der Pfad des Zertifikats für den Vermittlungsserver festgelegt:</span><span class="sxs-lookup"><span data-stu-id="3c2fa-113">The next example sets the path of the certificate for the Mediation Server:</span></span>
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a><span data-ttu-id="3c2fa-114">Beispiel 3</span><span class="sxs-lookup"><span data-stu-id="3c2fa-114">Example 3</span></span>

<span data-ttu-id="3c2fa-115">Im nächsten Beispiel wird das Zertifikat für den Vermittlungsserver aktualisiert:</span><span class="sxs-lookup"><span data-stu-id="3c2fa-115">The next example updates the certificate for the Mediation Server:</span></span>
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a><span data-ttu-id="3c2fa-116">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3c2fa-116">Detailed Description</span></span>
<span data-ttu-id="3c2fa-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="3c2fa-117"></span></span>

<span data-ttu-id="3c2fa-118">Bei der Bereitstellung oder beim Ändern der Topologie müssen Sie den Pfad für das Zertifikat des Edgeservers und optional des Vermittlungsservers angeben.</span><span class="sxs-lookup"><span data-stu-id="3c2fa-118">During the deployment, or while modifying the topology, you need to specify the path for the Edge Server certificate, and optionally for the Mediation Server certificate.</span></span> 
  
<span data-ttu-id="3c2fa-119">Das Zertifikat für den Vermittlungsserver ist erforderlich, wenn zwischen den Gateways und dem Vermittlungsserver TLS verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3c2fa-119">The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server.</span></span> <span data-ttu-id="3c2fa-120">Wenn Sie eine Cloud Connector-Appliance bereitstellen und TLS bereitstellen möchten, können Sie nur den Pfad zu dem Zertifikat angeben, das auf dem Vermittlungs Server bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="3c2fa-120">When you deploy a Cloud Connector appliance and want to deploy TLS, you can only specify the path to the certificate that will be deployed on the Mediation Server.</span></span> <span data-ttu-id="3c2fa-121">Wenn Sie jedoch das Vermittlungszertifikat in einer bereits bereitgestellten Appliance aktualisieren möchten, müssen Sie den Pfad und den Parameter „-Import“ angeben.</span><span class="sxs-lookup"><span data-stu-id="3c2fa-121">However, if you want to update the Mediation certificate on an already deployed appliance, you need to specify the path and the -Import parameter.</span></span> <span data-ttu-id="3c2fa-122">Um den Pfad anzuzeigen, verwenden Sie das Cmdlet „Get-CCExternalCertificateFilePath“.</span><span class="sxs-lookup"><span data-stu-id="3c2fa-122">To see the path, use the Get-CCExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="3c2fa-123">Parameter</span><span class="sxs-lookup"><span data-stu-id="3c2fa-123">Parameters</span></span>
<span data-ttu-id="3c2fa-124"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="3c2fa-124"></span></span>

|<span data-ttu-id="3c2fa-125">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="3c2fa-125">**Parameter**</span></span>|<span data-ttu-id="3c2fa-126">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="3c2fa-126">**Required**</span></span>|<span data-ttu-id="3c2fa-127">**Typ**</span><span class="sxs-lookup"><span data-stu-id="3c2fa-127">**Type**</span></span>|<span data-ttu-id="3c2fa-128">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="3c2fa-128">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="3c2fa-129"> Target</span><span class="sxs-lookup"><span data-stu-id="3c2fa-129">Target</span></span> <br/> | <span data-ttu-id="3c2fa-130">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="3c2fa-130">Required</span></span> <br/> |<span data-ttu-id="3c2fa-131">System.String</span><span class="sxs-lookup"><span data-stu-id="3c2fa-131">System.String</span></span>  <br/> |<span data-ttu-id="3c2fa-p103">Der Typ des angeforderten Dateipfads. Mögliche Typen:</span><span class="sxs-lookup"><span data-stu-id="3c2fa-p103">Type of file path requested. Types include:</span></span>  <br/> <span data-ttu-id="3c2fa-134">„EdgeServer“ (Standard)</span><span class="sxs-lookup"><span data-stu-id="3c2fa-134">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="3c2fa-135">„MediationServer“</span><span class="sxs-lookup"><span data-stu-id="3c2fa-135">MediationServer</span></span>  <br/> |
|<span data-ttu-id="3c2fa-136">Import</span><span class="sxs-lookup"><span data-stu-id="3c2fa-136">Import</span></span>  <br/> |<span data-ttu-id="3c2fa-137">Optional</span><span class="sxs-lookup"><span data-stu-id="3c2fa-137">Optional</span></span>  <br/> |<span data-ttu-id="3c2fa-138">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="3c2fa-138">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="3c2fa-p104">Gibt an, dass das Zertifikat auf dem Vermittlungsserver importiert werden muss. Dieser Parameter ist bei der ersten Bereitstellung einer Appliance nicht notwendig. Der Parameter ist erforderlich, wenn Sie das vorhandene Zertifikat einer bereits bereitgestellten Version ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="3c2fa-p104">Indicates that the certificate must be imported to the Mediation Server. This parameter is not needed if you deploy an appliance for first time. The parameter is required if you want to change the existing certificate on an already deployed version.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="3c2fa-142">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="3c2fa-142">Input Types</span></span>
<span data-ttu-id="3c2fa-143"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3c2fa-143"></span></span>

<span data-ttu-id="3c2fa-144">Das Cmdlet „Set-CcExternalCertificateFilePath“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="3c2fa-144">The Set-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="3c2fa-145">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="3c2fa-145">Return Types</span></span>
<span data-ttu-id="3c2fa-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3c2fa-146"></span></span>

<span data-ttu-id="3c2fa-147">Keine</span><span class="sxs-lookup"><span data-stu-id="3c2fa-147">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3c2fa-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c2fa-148">See also</span></span>
<span data-ttu-id="3c2fa-149"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3c2fa-149"></span></span>

[<span data-ttu-id="3c2fa-150">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="3c2fa-150">Get-CcExternalCertificateFilePath</span></span>](get-ccexternalcertificatefilepath.md)
  

