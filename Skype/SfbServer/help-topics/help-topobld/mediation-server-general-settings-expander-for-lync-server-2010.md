---
title: Allgemeine Einstellungen für den Vermittlungsserver für Lync Server 2010 – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'In diesem Dialogfeld bearbeiten Sie die Eigenschaften der Vermittlungsserver. Auf der linken Seite finden Sie eine Reihe von schnell Links, die Sie zu den Einstellungen für allgemeine Einstellungen, Einstellungen für den nächsten Hop und Einstellungen für das PSTN-Gateway führen. In jedem Abschnitt sind die folgenden Einstellungen zu finden:'
ms.openlocfilehash: ce58f0c64a458864c91bfd63f8b1d0f905d5374d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285716"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="f744a-105">Allgemeine Einstellungen für den Vermittlungsserver für Lync Server 2010 – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="f744a-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>

<span data-ttu-id="f744a-106">In diesem Dialogfeld bearbeiten Sie die Eigenschaften der Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="f744a-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="f744a-107">Auf der linken Seite finden Sie eine Reihe von schnell Links, die Sie zu den Einstellungen für allgemeine Einstellungen, Einstellungen für den nächsten Hop und Einstellungen für das PSTN-Gateway führen.</span><span class="sxs-lookup"><span data-stu-id="f744a-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="f744a-108">In jedem Abschnitt sind die folgenden Einstellungen zu finden:</span><span class="sxs-lookup"><span data-stu-id="f744a-108">In each section are the following settings:</span></span>

 <span data-ttu-id="f744a-109">**Allgemein**:</span><span class="sxs-lookup"><span data-stu-id="f744a-109">**General**:</span></span>

- <span data-ttu-id="f744a-110">**FQDN**: Sie bearbeiten den vollqualifizierten Domänennamen des Vermittlungsservers.</span><span class="sxs-lookup"><span data-stu-id="f744a-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>

- <span data-ttu-id="f744a-111">**Zuordnungen**: Aktivieren Sie das Kontrollkästchen **Edge-Pool zuordnen (für Medienkomponenten)** , und wählen Sie einen Edgeserver oder einen Edge-Pool aus, den der Vermittlungsserver als Medienpfad für den externen Zugriff verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="f744a-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>

  <span data-ttu-id="f744a-112">**Nächster Hop**:</span><span class="sxs-lookup"><span data-stu-id="f744a-112">**Next hop**:</span></span>

- <span data-ttu-id="f744a-113">**Auswahl für den nächsten Hop**: Wählen Sie in einer Liste den Front-End-Server oder den Front-End-Pool aus, der als Pfad für den Vermittlungsserver für die Kommunikation mit Ihrer Bereitstellung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f744a-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>

  <span data-ttu-id="f744a-114">**PSTN-Gateway**:</span><span class="sxs-lookup"><span data-stu-id="f744a-114">**PSTN gateway**:</span></span>

  <span data-ttu-id="f744a-115">**Vermittlungs Server-PSTN-Gateway**:</span><span class="sxs-lookup"><span data-stu-id="f744a-115">**Mediation Server PSTN gateway**:</span></span>

- <span data-ttu-id="f744a-116">**Abhör Anschlüsse**: definieren Sie die Ports, die vom Vermittlungs Server überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="f744a-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="f744a-117">Sie können einen Port für **TLS** oder Transport Layer Security oder **TCP**oder Transport Control Protocol definieren.</span><span class="sxs-lookup"><span data-stu-id="f744a-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="f744a-118">Damit der Port Eintrag für TCP verfügbar ist, müssen Sie das Kontrollkästchen für TCP- **Port aktivieren**aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f744a-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f744a-119">Informationen dazu finden Sie in den Dokumentations-und Konfigurationseinstellungen für das PSTN-Gateway (Public Switched Telephone Network), um festzustellen, ob Portwerte TLS, TCP oder beides aktiviert und definiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="f744a-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="f744a-120">TLS ist ein sichereres Protokoll, in dem der Datenverkehr zwischen dem Vermittlungs Server und dem PSTN-Gateway mithilfe von Zertifikaten verschlüsselt wird.</span><span class="sxs-lookup"><span data-stu-id="f744a-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="f744a-121">Nicht alle PSTN-Gateways unterstützen TLS.</span><span class="sxs-lookup"><span data-stu-id="f744a-121">Not all PSTN gateways support TLS.</span></span>

- <span data-ttu-id="f744a-122">Eine Liste der SIP-Trunks und der Gateways, die für Ihre Bereitstellung definiert und konfiguriert sind, wird aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="f744a-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="f744a-123">Wenn keine Einträge vorhanden sind, gibt es keine SIP-Trunks oder PSTN-Gateways, die für Ihre Bereitstellung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="f744a-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="f744a-124">Sie definieren und konfigurieren Trunks und Gateways unter **freigegebene Komponenten** im Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="f744a-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>

## <a name="see-also"></a><span data-ttu-id="f744a-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f744a-125">See also</span></span>

[<span data-ttu-id="f744a-126">Übersicht über SIP-Trunking</span><span class="sxs-lookup"><span data-stu-id="f744a-126">Overview of SIP Trunking</span></span>](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[<span data-ttu-id="f744a-127">Bereitstellungsoptionen für PSTN-Gateways</span><span class="sxs-lookup"><span data-stu-id="f744a-127">PSTN Gateway Deployment Options</span></span>](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
