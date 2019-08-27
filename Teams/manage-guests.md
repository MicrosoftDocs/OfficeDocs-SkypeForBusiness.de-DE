---
title: Verwalten des Gastzugriffs in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: IT-Administratoren können Gäste auf der Mandantenebene hinzufügen, Richtlinien und Berechtigungen für Gastbenutzer festlegen und verwalten, festlegen, welche Benutzer Gäste einladen können, und Berichte über Gastbenutzeraktivität abrufen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f3ede35352436074cbf7c94fc9df78100a73a017
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241810"
---
<a name="manage-guest-access-in-microsoft-teams"></a>Verwalten des Gastzugriffs in Microsoft Teams
======================================

**Gast** ist ein Benutzer-/Lizenztyp in Microsoft Teams, der in allen Office 365 Business Premium-, Office 365 Enterprise- und Office 365 Education-Abonnements enthalten ist. Eine zusätzliche Office 365-Lizenz ist nicht erforderlich. Der Gastzugriff auf Microsoft Teams ist eine Einstellung auf Mandantenebene, die standardmäßig deaktiviert ist. Weitere Details zum Gastzugriff finden Sie unter [Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams](set-up-guests.md).

Nachdem der **Gast**-Benutzer-/Lizenztyp aktiviert wurde, können Sie die Einstellungen für die Gäste über die in [Verwalten von Microsoft Teams-Einstellungen für Ihre Organisation](enable-features-office-365.md) und [Verwalten von Microsoft Teams während der Umstellung auf das neue Admin Center für Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md) beschriebenen Steuerelemente konfigurieren.     
    
IT-Administratoren können Gäste auf der Mandantenebene hinzufügen, Richtlinien und Berechtigungen für Gastbenutzer festlegen und verwalten und Berichte über Gastbenutzeraktivität abrufen. Diese Steuerelemente sind über das Microsoft Teams Admin Center verfügbar. Inhalte und Aktivitäten von Gastbenutzern unterliegen den gleichen Compliance-und Überwachungsfunktionen wie der Rest von Office 365.

Teambesitzer können neue Gäste einladen und vorhandene Gastbenutzer zu ihren Teams hinzufügen. Teambesitzer können Gastbenutzer über **Teams** > **Teams verwalten** identifizieren und kanalbezogene Funktionen für Gäste über **Organisationsweite Einstellungen** > **Gastzugriff** festlegen. Dazu gehört auch, Gästen das Erstellen, Aktualisieren und Löschen von Kanälen zu gestatten, wie in der folgenden Abbildung dargestellt.

![Einstellungen von Gastberechtigungen in Teams](media/manage-guest-access-image1.png)
  
Sie können das Azure Active Directory-Portal zum Verwalten von Gästen und deren Zugriff auf Office 365- und Teams-Ressourcen verwenden. Die Teams-Einstellung für Gastzugriff nutzt die Azure AD-B2B-Funktionen (Business-to-Business) zur Zusammenarbeit als zugrunde liegende Infrastruktur zum Speichern der Informationen über Sicherheitsprinzipien, wie zum Beispiel Einstellungen für Identitätseigenschaften, Mitgliedschaften und für die mehrstufige Authentifizierung. Weitere Informationen zu Azure AD B2B finden Sie unter [Was ist die Azure AD B2B-Zusammenarbeit?](https://go.microsoft.com/fwlink/p/?linkid=853011) und [Häufig gestellte Fragen zur Azure Active Directory B2B-Zusammenarbeit](https://go.microsoft.com/fwlink/p/?linkid=853020).

> [!NOTE]
> Microsoft Teams berücksichtigt immer externe Azure AD-Einstellungen, um das Hinzufügen von Gästen zum Mandanten zuzulassen bzw. zu verhindern. Weitere Informationen finden Sie unter [Autorisieren des Gastzugriffs in Microsoft Teams](Teams-dependencies.md).
  
## <a name="guest-access-vs-external-access-federation"></a>Gastzugriff und externer Zugriff (Partnerverbund) im Vergleich

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="review-guest-access-periodically"></a>Regelmäßige Überprüfung des Gastzugriffs

In Teams können Sie fünf Gäste für jeden lizenzierten Benutzer hinzufügen. Aufgrund dieser Einschränkung oder weil Sie den Mandanten auf dem neuesten Stand halten möchten, sollten Sie den Gastzugriff regelmäßig überprüfen, um Benutzer zu identifizieren, die Zugriff haben und diesen nicht mehr benötigen. Mit Azure AD können Sie eine Zugriffsüberprüfung für Mitglieder einer Gruppe oder Benutzer, die einer Anwendung zugewiesen sind, erstellen. Das Erstellen regelmäßiger Zugriffsüberprüfungen kann Zeit sparen. Wenn Sie Benutzer, die Zugriff auf eine Anwendung haben oder Mitglied einer Gruppe sind, routinemäßig überprüfen, können Sie die Häufigkeit dieser Überprüfungen definieren. 

Sie können selbst eine Überprüfung des Gastzugriffs durchführen, Gäste bitten, ihre eigene Mitgliedschaft zu überprüfen oder den Besitzer einer Anwendung bzw. einen Entscheidungsträger bitten, die Zugriffsüberprüfung durchzuführen. Verwenden Sie das Azure-Portal, um Überprüfungen des Gastzugriffs durchzuführen. Weitere Informationen finden Sie unter [Verwalten des Gastzugriffs mit Azure AD-Zugriffsüberprüfungen](https://docs.microsoft.com/de-DE/azure/active-directory/governance/manage-guest-access-with-access-reviews).

###  <a name="prerequisites"></a>Voraussetzungen

Zugriffsüberprüfungen sind mit der Premium P2-Edition von Azure AD (in Microsoft Enterprise Mobility + Security E5 enthalten) verfügbar. Weitere Informationen finden Sie unter [Azure Active Directory-Editionen](https://docs.microsoft.com/de-DE/azure/active-directory/fundamentals/active-directory-whatis). Jeder Benutzer, der mit diesem Feature interagiert (durch Erstellen oder Ausfüllen einer Überprüfung bzw. Bestätigen des Zugriffs), benötigt eine Lizenz.

Die Anzahl von Gästen, die Sie hinzufügen können, ist in Teams nicht beschränkt. Allerdings basiert die Gesamtzahl der Gäste, die Ihrem Mandanten hinzugefügt werden können, darauf, was gemäß Ihrer AAD-Lizenzierung zulässig ist. Weitere Informationen finden Sie unter [Lizenzierung für die Azure AD B2B-Zusammenarbeit](https://docs.microsoft.com/de-DE/azure/active-directory/b2b/licensing-guidance).

## <a name="guest-access-latencies"></a>Wartezeiten für den Gastzugriff

Die Gasteinstellungen werden in Azure AD festgelegt. Es dauert ca. 2 bis 24 Stunden, bis die Änderungen in der gesamten Office 365-Organisation wirksam werden. Wenn Benutzer versuchen, einen Gast zu ihrem Team hinzuzufügen, und dabei die Meldung „Wenden Sie sich an Ihren Administrator“ sehen, ist wahrscheinlich die Gastfunktion nicht aktiviert, oder die Einstellungen sind noch nicht wirksam.

## <a name="more-information"></a>Weitere Informationen

Informationen zur Verwendung von PowerShell zum Verwalten des Gastzugriffs finden Sie unter [Verwenden von PowerShell zum Steuern des Gastzugriffs auf ein Team](guest-access-powershell.md).


