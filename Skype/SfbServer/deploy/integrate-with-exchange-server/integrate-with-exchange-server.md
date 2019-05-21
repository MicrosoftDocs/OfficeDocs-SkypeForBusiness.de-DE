---
title: Integrieren von Skype for Business Server in Exchange Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 795dc1c6-524f-4012-8b66-103b55198044
description: 'Zusammenfassung: Überprüfen der Integrationsschritte für Exchange Server 2016 oder Exchange Server 2013 und Skype for Business Server.'
ms.openlocfilehash: 25b2260805cf4e42bc15d1ae5607baa3f830fba6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277986"
---
# <a name="integrate-skype-for-business-server-with-exchange-server"></a><span data-ttu-id="158fc-103">Integrieren von Skype for Business Server in Exchange Server</span><span class="sxs-lookup"><span data-stu-id="158fc-103">Integrate Skype for Business Server with Exchange Server</span></span>

<span data-ttu-id="158fc-104">**Zusammenfassung:** Überprüfen Sie die Integrationsschritte für Exchange Server 2013 oder höher und Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="158fc-104">**Summary:** Review integration steps for Exchange Server 2013 or later and Skype for Business Server.</span></span>

<span data-ttu-id="158fc-105">Exchange Server 2013 oder höher und Skype for Business Server sind kompatibel und gut integriert.</span><span class="sxs-lookup"><span data-stu-id="158fc-105">Exchange Server 2013 or later and Skype for Business Server are compatible and integrate well.</span></span> <span data-ttu-id="158fc-106">Beispielsweise können die Anwesenheitsinformationen von Skype for Business-Benutzern in Microsoft Outlook gemeldet werden. Ebenso kann Skype for Business auf den Outlook-Kalender eines Benutzers zugreifen, feststellen, dass der Benutzer eine Besprechung geplant hat, und die Anwesenheit des Benutzers während der Besprechung als "beschäftigt" anzeigen.</span><span class="sxs-lookup"><span data-stu-id="158fc-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="158fc-107">Obwohl Sie Exchange Server nicht ausführen müssen, um Skype for Business Server (oder umgekehrt) auszuführen, verbessern die beiden Produkte zusammen die Benutzeroberfläche des jeweiligen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="158fc-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>

<span data-ttu-id="158fc-108">Diese Dokumentation enthält Informationen zur Integration von Skype for Business Server und Exchange Server 2016 oder Exchange Server 2013, es wird jedoch davon ausgegangen, dass die anfängliche Einrichtung und Konfiguration dieser beiden Produkte bereits erfolgte.</span><span class="sxs-lookup"><span data-stu-id="158fc-108">This documentation provides information on integrating Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="158fc-109">Weitere Informationen zur Bereitstellung von Skype for Business Server finden Sie im [Skype for Business Server Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span><span class="sxs-lookup"><span data-stu-id="158fc-109">For details about deploying Skype for Business Server see the [Skype for Business Server Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span></span> <span data-ttu-id="158fc-110">Details zum Bereitstellen von Exchange Server finden Sie in der Bereitstellungsdokumentation für Ihre Exchange-Version.</span><span class="sxs-lookup"><span data-stu-id="158fc-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>

<span data-ttu-id="158fc-111">Wenn Sie eine lokale Installation von Skype for Business Server mit Microsoft Exchange Online integrieren, lesen Sie [Konfigurieren der Integration zwischen lokalen Skype for Business-Servern und Outlook Web App](outlook-web-app.md).</span><span class="sxs-lookup"><span data-stu-id="158fc-111">If you are integrating an on premises installation of Skype for Business Server with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server and Outlook Web App](outlook-web-app.md).</span></span>

<span data-ttu-id="158fc-112">Wenn Sie Skype for Business Online mit Exchange Server lokal integrieren, lesen Sie [Konfigurieren von OAuth zwischen Skype for Business Online und Exchange lokal](oauth-with-online-and-on-premises.md).</span><span class="sxs-lookup"><span data-stu-id="158fc-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="158fc-113">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="158fc-113">In this section</span></span>

[<span data-ttu-id="158fc-114">Konfigurieren von Partneranwendungen in Skype for Business Server und Exchange Server</span><span class="sxs-lookup"><span data-stu-id="158fc-114">Configure partner applications in Skype for Business Server and Exchange Server</span></span>](configure-partner-applications.md)

[<span data-ttu-id="158fc-115">Konfigurieren von Skype for Business Server für die Verwendung der Exchange Server-Archivierung</span><span class="sxs-lookup"><span data-stu-id="158fc-115">Configure Skype for Business Server to use Exchange Server archiving</span></span>](use-exchange-archiving.md)

[<span data-ttu-id="158fc-116">Konfigurieren von SharePoint Server für die Suche nach archivierten Skype for Business-Daten</span><span class="sxs-lookup"><span data-stu-id="158fc-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)

[<span data-ttu-id="158fc-117">Konfigurieren von Skype for Business Server für die Verwendung des einheitlichen Kontaktspeichers</span><span class="sxs-lookup"><span data-stu-id="158fc-117">Configure Skype for Business Server to use the unified contact store</span></span>](use-the-unified-contact-store.md)

[<span data-ttu-id="158fc-118">Konfigurieren der Verwendung von Fotos mit hoher Auflösung in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="158fc-118">Configure the use of high-resolution photos in Skype for Business Server</span></span>](high-resolution-photos.md)

[<span data-ttu-id="158fc-119">Konfigurieren von Exchange Server Unified Messaging für Skype for Business Server-Voicemail</span><span class="sxs-lookup"><span data-stu-id="158fc-119">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)

[<span data-ttu-id="158fc-120">Integration von Skype for Business Server und Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="158fc-120">Integrating Skype for Business Server and Microsoft Outlook Web App 2013</span></span>](https://technet.microsoft.com/library/513d4cc7-aa87-4f68-b99d-d58b63bdf242.aspx)

[<span data-ttu-id="158fc-121">Konfigurieren des persönlichen Kontaktspeichers auf Clientcomputern für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="158fc-121">Configure the personal contacts store on client computers for Skype for Business Server</span></span>](personal-contacts-store.md)

## <a name="see-also"></a><span data-ttu-id="158fc-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="158fc-122">See also</span></span>

[<span data-ttu-id="158fc-123">Plan zur Integration von Skype for Business mit Exchange Server</span><span class="sxs-lookup"><span data-stu-id="158fc-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
