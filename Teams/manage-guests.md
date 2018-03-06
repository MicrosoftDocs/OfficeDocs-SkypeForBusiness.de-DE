---
title: Verwalten des Gastzugriffs in Microsoft Teams
author: LaithAlShamri
ms.author: laal
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
ms.reviewer: laal
description: "IT-Administratoren können Gäste auf der Mandantenebene hinzufügen, Richtlinien und Berechtigungen für Gastbenutzer festlegen und verwalten, festlegen, welche Benutzer Gäste einladen können, und Berichte über Gastbenutzeraktivität abrufen."
appliesto:
- Microsoft Teams
ms.openlocfilehash: ed42a6f4578786f6f5ed9683cf92c3b915653d66
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2018
---
<a name="manage-guest-access-to-microsoft-teams"></a><span data-ttu-id="ee0fa-103">Verwalten des Gastzugriffs in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ee0fa-103">Manage guest access to Microsoft Teams</span></span>
======================================

<span data-ttu-id="ee0fa-104">Gastzugriff ist in allen Office 365 Business Premium-, Office 365 Enterprise- und Office 365 Education-Abonnements enthalten.</span><span class="sxs-lookup"><span data-stu-id="ee0fa-104">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="ee0fa-105">Eine zusätzliche Office 365-Lizenz ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ee0fa-105">No additional Office 365 license is necessary.</span></span>
  
    
    
<span data-ttu-id="ee0fa-106">Der Gastzugriff auf Microsoft Teams ist eine Einstellung auf Mandantenebene, die standardmäßig deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ee0fa-106">Teams guest access is a tenant-level setting and is turned off by default.</span></span> <span data-ttu-id="ee0fa-107">IT-Administratoren können Gäste auf der Mandantenebene hinzufügen, Richtlinien und Berechtigungen für Gastbenutzer festlegen und verwalten, festlegen, welche Benutzer Gäste einladen können, und Berichte über Gastbenutzeraktivität abrufen.</span><span class="sxs-lookup"><span data-stu-id="ee0fa-107">IT admins can add guests at the tenant level, set and manage guest user policies and permissions, determine which users can invite guests, and pull reports on guest user activity.</span></span> <span data-ttu-id="ee0fa-108">Diese Steuerelemente sind über das Office 365 Admin Center verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ee0fa-108">These controls are available through the Office 365 admin center.</span></span> <span data-ttu-id="ee0fa-109">Inhalte und Aktivitäten von Gastbenutzern unterliegen dem gleichen Compliance- und Überwachungsschutz wie der Rest von Office 365.</span><span class="sxs-lookup"><span data-stu-id="ee0fa-109">Guest user content and activities are under the same compliance and auditing protection as the rest of Office 365.</span></span>
  
    
    

> [!NOTE]
> <span data-ttu-id="ee0fa-110">Die Mandanteneinstellung für den Gastzugriff auf Microsoft Teams verhindert nur die Gastanmeldung.</span><span class="sxs-lookup"><span data-stu-id="ee0fa-110">The Teams guest access tenant setting only prevents guest sign-in.</span></span> <span data-ttu-id="ee0fa-111">Teambesitzer können neue Gäste einladen und vorhandene Gastbenutzer zu ihren jeweiligen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ee0fa-111">Team owners will be able to invite new guests and add existing directory guest users to their respective teams.</span></span> <span data-ttu-id="ee0fa-112">Zur Erinnerung: Teams berücksichtigt immer externe Azure Active Directory-Einstellungen, um das Hinzufügen von Gästen zum Mandanten zuzulassen bzw. zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="ee0fa-112">As a reminder, Teams always honors Azure Active Directory external settings to allow or prevent guest user addition to the tenant.</span></span> 
  
    
    

<span data-ttu-id="ee0fa-113">Zudem können Sie das Azure Active Directory-Portal zum Verwalten von Gästen und deren Zugriff auf Office 365- und Teams-Ressourcen verwenden.</span><span class="sxs-lookup"><span data-stu-id="ee0fa-113">In addition, you can use the Azure Active Directory portal to manage guests and their access to Office 365 and Teams resources.</span></span> <span data-ttu-id="ee0fa-114">Die Teams-Einstellung für Gastzugriff nutzt die Azure Active Directory-B2B-Funktionen (Business-to-Business) zur Zusammenarbeit als zugrunde liegende Infrastruktur zum Speichern der Informationen über Sicherheitsprinzipien, wie zum Beispiel Einstellungen für Identitätseigenschaften, Mitgliedschaften und für die mehrstufige Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="ee0fa-114">Teams guest access makes use of Azure Active Directory business-to-business (B2B) collaboration capabilities as the underlying infrastructure to store security principles information such as identity properties, memberships, and multi-factor authentication settings.</span></span> <span data-ttu-id="ee0fa-115">Weitere Informationen zu Azure Active Directory B2B finden Sie unter [Was ist die Azure AD B2B-Zusammenarbeit?](https://go.microsoft.com/fwlink/p/?linkid=853011) und [Häufig gestellte Fragen zur Azure Active Directory B2B-Zusammenarbeit](https://go.microsoft.com/fwlink/p/?linkid=853020).</span><span class="sxs-lookup"><span data-stu-id="ee0fa-115">To learn more about Azure Active Directory B2B, see [What is Azure AD B2B collaboration?](https://go.microsoft.com/fwlink/p/?linkid=853011) and [Azure Active Directory B2B collaboration FAQs](https://go.microsoft.com/fwlink/p/?linkid=853020).</span></span>
  