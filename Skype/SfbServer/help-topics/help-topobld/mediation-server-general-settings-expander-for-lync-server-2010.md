---
title: Allgemeine Einstellungen für den Vermittlungsserver für Lync Server 2010 – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'In diesem Dialogfeld bearbeiten Sie die Eigenschaften der Vermittlungsserver. Auf der linken Seite befinden sich mehrere direkte Links zu den Einstellungen unter "Allgemein", "Einstellungen für nächsten Hop" und "Einstellungen für PSTN-Gateway". In jedem Abschnitt sind die folgenden Einstellungen enthalten:'
ms.openlocfilehash: 19687f8d6a97a9174782c094f80c5b52d6973caf
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215156"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="c77cf-105">Allgemeine Einstellungen für den Vermittlungsserver für Lync Server 2010 – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="c77cf-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>

<span data-ttu-id="c77cf-106">In diesem Dialogfeld bearbeiten Sie die Eigenschaften der Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="c77cf-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="c77cf-107">Auf der linken Seite befinden sich mehrere direkte Links zu den Einstellungen unter "Allgemein", "Einstellungen für nächsten Hop" und "Einstellungen für PSTN-Gateway".</span><span class="sxs-lookup"><span data-stu-id="c77cf-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="c77cf-108">In jedem Abschnitt sind die folgenden Einstellungen enthalten:</span><span class="sxs-lookup"><span data-stu-id="c77cf-108">In each section are the following settings:</span></span>

 <span data-ttu-id="c77cf-109">**Allgemein**:</span><span class="sxs-lookup"><span data-stu-id="c77cf-109">**General**:</span></span>

- <span data-ttu-id="c77cf-110">**FQDN**: Sie bearbeiten den vollqualifizierten Domänennamen des Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="c77cf-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>

- <span data-ttu-id="c77cf-111">**Zuordnungen**: Aktivieren Sie das Kontrollkästchen **Edgepool zuordnen (für Medienkomponenten)** , und wählen Sie eine Edgeserver oder Edgepool aus, die der Vermittlungsserver als Medienpfad für den externen Zugriff verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="c77cf-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>

  <span data-ttu-id="c77cf-112">**Nächster Hop**:</span><span class="sxs-lookup"><span data-stu-id="c77cf-112">**Next hop**:</span></span>

- <span data-ttu-id="c77cf-113">**Auswahl für nächsten Hop**: Wählen Sie in einer Liste die Front-End-Server oder Front-End-Pool aus, die als Pfad für die Vermittlungsserver verwendet werden sollen, die für die Kommunikation mit Ihrer Bereitstellung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c77cf-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>

  <span data-ttu-id="c77cf-114">**PSTN-Gateway**:</span><span class="sxs-lookup"><span data-stu-id="c77cf-114">**PSTN gateway**:</span></span>

  <span data-ttu-id="c77cf-115">**PSTN-Gateway für Vermittlungsserver**:</span><span class="sxs-lookup"><span data-stu-id="c77cf-115">**Mediation Server PSTN gateway**:</span></span>

- <span data-ttu-id="c77cf-116">**Abhör Anschlüsse**: definieren Sie die Ports, auf denen die Vermittlungsserver überwacht werden soll.</span><span class="sxs-lookup"><span data-stu-id="c77cf-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="c77cf-117">Sie können einen Port für **TLS** (Transport Layer Security) oder **TCP** (Transport Control Protocol) definieren.</span><span class="sxs-lookup"><span data-stu-id="c77cf-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="c77cf-118">Damit der Porteintrag für TCP verfügbar ist, müssen Sie das Kontrollkästchen **TCP-Port aktivieren** aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c77cf-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c77cf-119">Ermitteln Sie anhand der Dokumentation und Konfigurationseinstellungen für das PSTN-Gateway (Public Switched Telephone Network), ob Sie Portwerte für TLS, TCP oder beides aktivieren und definieren müssen.</span><span class="sxs-lookup"><span data-stu-id="c77cf-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="c77cf-120">TLS ist ein sichereres Protokoll, das Zertifikate verwendet, um den Datenverkehr zwischen dem Vermittlungsserver und dem PSTN-Gateway zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="c77cf-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="c77cf-121">Nicht alle PSTN-Gateways unterstützen TLS.</span><span class="sxs-lookup"><span data-stu-id="c77cf-121">Not all PSTN gateways support TLS.</span></span>

- <span data-ttu-id="c77cf-122">Es ist eine Liste mit SIP-Trunks und den Gateways angegeben, die für die Bereitstellung definiert und konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="c77cf-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="c77cf-123">Falls keine Einträge vorhanden sind, sind für die Bereitstellung keine SIP-Trunks oder PSTN-Gateways konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="c77cf-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="c77cf-124">Sie definieren und konfigurieren Trunks und Gateways unter **freigegebene Komponenten** im Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="c77cf-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>

## <a name="see-also"></a><span data-ttu-id="c77cf-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c77cf-125">See also</span></span>

[<span data-ttu-id="c77cf-126">Übersicht über SIP-Trunking</span><span class="sxs-lookup"><span data-stu-id="c77cf-126">Overview of SIP Trunking</span></span>](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[<span data-ttu-id="c77cf-127">Bereitstellungsoptionen für PSTN-Gateways</span><span class="sxs-lookup"><span data-stu-id="c77cf-127">PSTN Gateway Deployment Options</span></span>](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
