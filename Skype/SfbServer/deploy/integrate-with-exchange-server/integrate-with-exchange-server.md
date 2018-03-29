---
title: Integrieren von Skype for Business Server 2015 mit Exchange Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 795dc1c6-524f-4012-8b66-103b55198044
description: 'Zusammenfassung: Überprüfen Sie Integrationsschritte für Exchange Server 2016 oder Exchange Server 2013 und Skype für Business Server 2015.'
ms.openlocfilehash: c8cbecd6b78e3dc14ad2133a93d9fc2d1f6bb3d6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="integrate-skype-for-business-server-2015-with-exchange-server"></a><span data-ttu-id="f6e8e-103">Integrieren von Skype for Business Server 2015 mit Exchange Server</span><span class="sxs-lookup"><span data-stu-id="f6e8e-103">Integrate Skype for Business Server 2015 with Exchange Server</span></span>
 
<span data-ttu-id="f6e8e-104">**Zusammenfassung:** Überprüfen Sie Integrationsschritte für Exchange Server 2016 oder Exchange Server 2013 und Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f6e8e-104">**Summary:** Review integration steps for Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="f6e8e-105">Exchange Server 2016 oder Exchange Server 2013 und Skype für Business Server 2015 kompatibel sind, und auch integrieren.</span><span class="sxs-lookup"><span data-stu-id="f6e8e-105">Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server 2015 are compatible and integrate well.</span></span> <span data-ttu-id="f6e8e-106">Beispielsweise kann Skype für Business Benutzer Anwesenheitsinformationen in Microsoft Outlook ausgegeben werden. Ebenso kann Skype für Unternehmen Zugriff auf Outlook-Kalender des Benutzers, beachten Sie, dass der Benutzer eine Besprechung geplant hat und Anwesenheitsstatus beschäftigt des Benutzers während der Besprechung anzeigen.</span><span class="sxs-lookup"><span data-stu-id="f6e8e-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="f6e8e-107">Obwohl Sie keine Exchange Server ausgeführt werden, um Skype für Business Server (oder umgekehrt) die beiden Produkte gemeinsam ausgeführt verbessern des jeweils anderen Benutzer wünschen.</span><span class="sxs-lookup"><span data-stu-id="f6e8e-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>
  
<span data-ttu-id="f6e8e-108">Diese Dokumentation enthält Informationen zur Integration von Skype für Business Server 2015 und Exchange Server 2016 oder Exchange Server 2013 jedoch angenommen, dass die anfängliche Einrichtung und Konfiguration dieser beiden Produkte bereits stattgefunden hat.</span><span class="sxs-lookup"><span data-stu-id="f6e8e-108">This documentation provides information on integrating Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="f6e8e-109">Ausführliche Informationen zum Bereitstellen von Skype für Business Server 2015 finden Sie unter der [Skype für Business Server 2015 Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span><span class="sxs-lookup"><span data-stu-id="f6e8e-109">For details about deploying Skype for Business Server 2015 see the [Skype for Business Server 2015 Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span></span> <span data-ttu-id="f6e8e-110">Ausführliche Informationen zur Bereitstellung von Exchange Server finden Sie in der Dokumentation zur Bereitstellung für Ihre Version von Exchange.</span><span class="sxs-lookup"><span data-stu-id="f6e8e-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>
  
<span data-ttu-id="f6e8e-111">Wenn Sie eine lokalen Installation von Skype für Business Server 2015 mit Microsoft Exchange Online integrieren, finden Sie unter [Konfigurieren der Integration zwischen lokalen Skype für Business Server 2015 und Outlook Web App](outlook-web-app.md).</span><span class="sxs-lookup"><span data-stu-id="f6e8e-111">If you are integrating an on premises installation of Skype for Business Server 2015 with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](outlook-web-app.md).</span></span>
  
<span data-ttu-id="f6e8e-112">Wenn Sie Skype für Business Online mit Exchange Server lokal integrieren, finden Sie unter [Konfigurieren von OAuth zwischen Skype für Business Online und Exchange lokal](oauth-with-online-and-on-premises.md).</span><span class="sxs-lookup"><span data-stu-id="f6e8e-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="f6e8e-113">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="f6e8e-113">In this section</span></span>

[<span data-ttu-id="f6e8e-114">Konfigurieren von partneranwendungen in Skype für Business Server 2015 und Exchange Server</span><span class="sxs-lookup"><span data-stu-id="f6e8e-114">Configure partner applications in Skype for Business Server 2015 and Exchange Server</span></span>](configure-partner-applications.md)
  
[<span data-ttu-id="f6e8e-115">Konfigurieren von Skype für Business Server 2015 mit Exchange Server-Archivierung</span><span class="sxs-lookup"><span data-stu-id="f6e8e-115">Configure Skype for Business Server 2015 to use Exchange Server archiving</span></span>](use-exchange-archiving.md)
  
[<span data-ttu-id="f6e8e-116">Konfigurieren von SharePoint Server zu suchenden archivierten Skype für Geschäftsdaten</span><span class="sxs-lookup"><span data-stu-id="f6e8e-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)
  
[<span data-ttu-id="f6e8e-117">Konfigurieren von Skype für Business Server 2015 einheitlichen Kontaktspeicher verwenden</span><span class="sxs-lookup"><span data-stu-id="f6e8e-117">Configure Skype for Business Server 2015 to use the unified contact store</span></span>](use-the-unified-contact-store.md)
  
[<span data-ttu-id="f6e8e-118">Konfigurieren Sie die Verwendung von hoch auflösenden Fotos in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f6e8e-118">Configure the use of high-resolution photos in Skype for Business Server 2015</span></span>](high-resolution-photos.md)
  
[<span data-ttu-id="f6e8e-119">Konfigurieren von Exchange Server Unified Messaging für Skype für Voicemail Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f6e8e-119">Configure Exchange Server Unified Messaging for Skype for Business Server 2015 voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)
  
[<span data-ttu-id="f6e8e-120">Integrieren von Skype für Business Server 2015 und Microsoft Outlook App 2013 Web</span><span class="sxs-lookup"><span data-stu-id="f6e8e-120">Integrating Skype for Business Server 2015 and Microsoft Outlook Web App 2013</span></span>](http://technet.microsoft.com/library/513d4cc7-aa87-4f68-b99d-d58b63bdf242.aspx)
  
[<span data-ttu-id="f6e8e-121">Konfigurieren Sie den Speicher für persönliche Kontakte auf den Clientcomputern für Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f6e8e-121">Configure the personal contacts store on client computers for Skype for Business Server 2015</span></span>](personal-contacts-store.md)
  
## <a name="see-also"></a><span data-ttu-id="f6e8e-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6e8e-122">See also</span></span>

#### 

[<span data-ttu-id="f6e8e-123">Planen der Integration von Skype für Unternehmen und Exchange</span><span class="sxs-lookup"><span data-stu-id="f6e8e-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)

