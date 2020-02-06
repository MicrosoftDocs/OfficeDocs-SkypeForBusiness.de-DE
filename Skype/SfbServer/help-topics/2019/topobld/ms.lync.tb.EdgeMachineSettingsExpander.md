---
title: Edgecomputereinstellungen – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
ROBOTS: NOINDEX, NOFOLLOW
description: 'Gehen Sie wie folgt vor, um die Eigenschaften für einen Server in einem Pool von Edge-Servern zu bearbeiten:'
ms.openlocfilehash: 1b2fce33b65e744c8ba2f18107d4f6bc5369b8de
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793803"
---
# <a name="edge-machine-settings-expander"></a>Edgecomputereinstellungen – Erweiterung
 
Gehen Sie wie folgt vor, um die Eigenschaften für einen Server in einem Pool von Edge-Servern zu bearbeiten:
  
Der **interne Name oder FQDN** kann geändert werden, indem Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) bearbeiten. Der FQDN muss mit dem Domänennamen-Host (A)-Eintrag (Domain Name System) und dem Antragstellernamen des Zertifikats übereinstimmen, das dem Server für die interne Edge-Netzwerkschnittstelle zugewiesen ist. Der Wert der **internen IP-Adresse** definiert die IP-Adresse, der die Netzwerkschnittstelle zugeordnet ist, die im Verhältnis zum Umkreisnetzwerk Entwurf als internes Netzwerk definiert ist.
  
In den nächsten drei Abschnitten des Dialogfelds werden die IP-Adressen für die externe Konfiguration dieses Edgeserver definiert. Die Möglichkeit zum Ändern der IP-Adressen ist von der Einstellung **Aktivieren des separaten FQDN und der IP-Adresse für Webkonferenzen und A/V** in den Eigenschafteneinstellungen auf der Poolebene des Edge-Servers betroffen.
  
## <a name="sip-access"></a>SIP-Zugriff

Bearbeiten Sie die externe IP-Adresse, die der Netzwerkschnittstelle für den SIP-Zugriff (Session Initiation Protocol) zugewiesen ist. Bei dieser IP-Adresse kann es sich entweder um eine öffentliche IP-Adresse oder eine Adresse im privaten IP-Adressbereich handeln.
  
> [!NOTE]
> Wenn die Einstellung **separater FQDN und IP-Adresse für Webkonferenzen und A/V** auf der Seite Pooleinstellungen aktivieren aktiviert ist, steht nur die IP-Adresse für den SIP-Zugriff zur Bearbeitung zur Verfügung.
  
## <a name="web-conferencing"></a>Webkonferenzen

Bearbeiten Sie die externe IP-Adresse, die der Netzwerkschnittstelle für Webkonferenzen zugewiesen ist. Bei dieser IP-Adresse kann es sich entweder um eine öffentliche IP-Adresse oder eine Adresse im privaten IP-Adressbereich handeln.
  
## <a name="audiovideo"></a>Audio/Video

Bearbeiten Sie die externe IP-Adresse, die der Netzwerkschnittstelle für Audio/Video (A/V) zugewiesen ist. Bei dieser IP-Adresse kann es sich entweder um eine öffentliche IP-Adresse oder eine Adresse im privaten IP-Adressbereich handeln.
  
Die Einstellung für die **verwendete NAT-aktivierte öffentliche IP-Adresse** ist die öffentliche Adresse, die von der externen Schnittstelle für die A/V-Netzwerkschnittstelle oder den Edgeserver im Allgemeinen verwendet wird. Wenn die Einstellung **separater FQDN und IP-Adresse für Webkonferenzen aktivieren und A/V** aktiviert ist, wird diese öffentliche IP-Adresse für alle drei externen Schnittstellen verwendet.
  

