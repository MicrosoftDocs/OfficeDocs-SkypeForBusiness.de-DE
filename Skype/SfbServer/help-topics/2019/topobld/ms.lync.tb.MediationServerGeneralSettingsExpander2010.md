---
title: Mediation Server Allgemeine Einstellungen – Erweiterung für Lync Server 2010
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'Sie können die Eigenschaften der Mediation Server in diesem Dialogfeld bearbeiten. Auf der linken Seite ist eine Reihe von Quicklinks zu gelangen Sie zur Einstellungen für allgemeine Einstellungen, die Einstellungen für den nächsten Hop und Einstellungen für PSTN-Gateway. In jedem Abschnitt sind die folgenden Einstellungen:'
ms.openlocfilehash: 39e9f57efd695c7bb90386dddc3f106106bb867e
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/21/2018
ms.locfileid: "19990975"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="2b27c-105">Mediation Server Allgemeine Einstellungen – Erweiterung für Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="2b27c-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="2b27c-106">Sie können die Eigenschaften der Mediation Server in diesem Dialogfeld bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="2b27c-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="2b27c-107">Auf der linken Seite ist eine Reihe von Quicklinks zu gelangen Sie zur Einstellungen für allgemeine Einstellungen, die Einstellungen für den nächsten Hop und Einstellungen für PSTN-Gateway.</span><span class="sxs-lookup"><span data-stu-id="2b27c-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="2b27c-108">In jedem Abschnitt sind die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="2b27c-108">In each section are the following settings:</span></span>
  
 <span data-ttu-id="2b27c-109">**Allgemein**:</span><span class="sxs-lookup"><span data-stu-id="2b27c-109">**General**:</span></span>
  
- <span data-ttu-id="2b27c-110">**FQDN**: Bearbeiten Sie den vollqualifizierten Domänennamen des Vermittlungsservers</span><span class="sxs-lookup"><span data-stu-id="2b27c-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>
    
- <span data-ttu-id="2b27c-111">**Zuordnungen**: Aktivieren Sie das Kontrollkästchen **edgepool zuordnen (für Medienkomponenten)** , und wählen Sie eine Edge-Server oder einem Edge-Pools für den Vermittlungsserver als Medienpfad für den externen Zugriff verwendet.</span><span class="sxs-lookup"><span data-stu-id="2b27c-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>
    
 <span data-ttu-id="2b27c-112">**Nächster Hop**:</span><span class="sxs-lookup"><span data-stu-id="2b27c-112">**Next hop**:</span></span>
  
- <span data-ttu-id="2b27c-113">**Auswahl für nächsten Hop**: den Front-End-Server oder Front-End-Pool als den Pfad für den Vermittlungsserver verwendet werden, um für die Kommunikation mit der Bereitstellung zu verwendende aus einer Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="2b27c-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>
    
 <span data-ttu-id="2b27c-114">**PSTN-Gateway**:</span><span class="sxs-lookup"><span data-stu-id="2b27c-114">**PSTN gateway**:</span></span>
  
 <span data-ttu-id="2b27c-115">**Mediation Server PSTN-Gateway**:</span><span class="sxs-lookup"><span data-stu-id="2b27c-115">**Mediation Server PSTN gateway**:</span></span>
  
- <span data-ttu-id="2b27c-116">**Überwachungsports**: Definieren Sie die Ports, die der Vermittlungsserver überwacht wird.</span><span class="sxs-lookup"><span data-stu-id="2b27c-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="2b27c-117">Sie können einen Port für **TLS** oder Transport Layer Security oder **TCP**, definieren oder transport Control-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="2b27c-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="2b27c-118">Für den Porteintrag für TCP verfügbar sein soll müssen Sie das Kontrollkästchen für **Aktivieren TCP-Port**auswählen.</span><span class="sxs-lookup"><span data-stu-id="2b27c-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="2b27c-119">Finden Sie in der Dokumentation und Konfiguration Einstellungen für Ihre Gateway public switched Telephone Network, (PSTN) zu ermitteln, wenn Sie bei aktivierter definieren müssen Port TLS, TCP oder beide Werte.</span><span class="sxs-lookup"><span data-stu-id="2b27c-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="2b27c-120">TLS ist eine sicherere Protokoll, Verwendung von Zertifikaten zur Verschlüsselung des Datenverkehrs zwischen dem Vermittlungsserver und PSTN-Gateway.</span><span class="sxs-lookup"><span data-stu-id="2b27c-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="2b27c-121">Nicht alle PSTN-Gateways unterstützt TLS.</span><span class="sxs-lookup"><span data-stu-id="2b27c-121">Not all PSTN gateways support TLS.</span></span> 
  
- <span data-ttu-id="2b27c-122">Eine Liste der SIP-Trunks und Gateways, die definiert und für Ihre Bereitstellung konfiguriert sind, wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2b27c-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="2b27c-123">Wenn keine Einträge vorhanden sind, sind keine SIP-Trunks oder PSTN-Gateways für die Bereitstellung konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="2b27c-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="2b27c-124">Sie definieren und Konfigurieren von Trunks und **Freigegebene Komponenten** -Gateways im Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="2b27c-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2b27c-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b27c-125">See also</span></span>

[<span data-ttu-id="2b27c-126">Übersicht über SIP-Trunking</span><span class="sxs-lookup"><span data-stu-id="2b27c-126">Overview of SIP Trunking</span></span>](http://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)
  
[<span data-ttu-id="2b27c-127">Bereitstellungsoptionen für PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="2b27c-127">PSTN Gateway Deployment Options</span></span>](http://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)