---
title: Konfigurieren von hybridkonnektivität
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Anleitung für die Implementierung von hybridkonnektivität zwischen Skype für Business Server und Skype für Business Online.
ms.openlocfilehash: a85b899407971ebdad0ac4c46096a6feade3fbcd
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839559"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Konfigurieren von hybridkonnektivität zwischen Skype für Business Server und Office 365
 
**Zusammenfassung:** Lesen Sie dieses Thema, um Informationen zum Konfigurieren von hybridkonnektivität zwischen Skype für Business Server und Skype für Business Online oder Teams.  Hybridkonnektivität können Sie Ihre lokalen Benutzer zu Skype für Business Online oder Teams zu verschieben, und ermöglicht es Benutzern Cloud-Dienste nutzen.
  
Bevor Sie die Schritte in diesem Thema ausführen, sollten Sie [Planen hybridkonnektivität zwischen Skype für Business Server und Office 365](plan-hybrid-connectivity.md)gelesen haben.
  
Die folgende Tabelle enthält die erforderlichen Aufgaben zum Konfigurieren von Skype für Business hybridkonnektivität und enthält Links zu verwandten Artikeln Weitere Informationen.
  
|**Schritt**|**Beschreibung**|
|:-----|:-----|
|Erstellen Sie ein Konto Mandanten für Office 365 und aktivieren Skype für Business Online  <br/> |Informationen Sie zu Office 365 und Skype für Business Online unter [Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Machen Sie sich mit den [Systemanforderungen](https://products.office.com/en-US/office-system-requirements) vertraut, um sicherzustellen, dass Ihre Umgebung für Office 365 bereit ist.  <br/> Einzelheiten zum Einrichten von Office 365 finden Sie unter [Erste Schritte mit Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Fügen Sie Ihrer Domäne zu Office 365-Mandanten hinzu und verifizieren Sie des Eigentums an  <br/> | Sie müssen Ihre Domäne dem Office 365-Mandanten hinzufügen und dann den Schritten zum Überprüfen der Domäne mit Office 365 folgen. Anhand dieser Schritte soll bestätigt werden, dass Sie der Besitzer der Domäne sind. <br/> Befolgen Sie die Schritte unter [Hinzufügen einer Domäne zu Office 365](https://support.office.com/en-us/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US), zum Hinzufügen Ihrer Domäne zu Office 365-Mandanten.  <br/> |
|Vorbereiten der Active Directory-Synchronisierung  <br/> |Active Directory-Synchronisierung vermeidet eine Verbindung zwischen Ihrer lokalen Active Directory ständig mit Office 365 synchronisiert. Hiermit können Sie erstellte synchronisiert Versionen der einzelnen Benutzerkonto und der Gruppe, und auch ermöglicht globale adresslist (GAL) Synchronisierung aus Ihrer lokalen Microsoft Exchange Server-Umgebung zu Microsoft Exchange Online verwendet. Weitere Informationen finden Sie unter [integrieren Ihre lokale Verzeichnisse mit Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).  <br/>  **Wichtig:** Sie müssen die Active Directory-Konten für alle Skype für Unternehmensbenutzer in Ihrer Organisation zwischen Ihrer lokalen und online-Bereitstellungen, synchronisieren, auch wenn der Benutzer nicht in Skype für Business Online verschoben werden. Wenn Sie nicht alle Benutzer synchronisieren, funktioniert die Kommunikation zwischen lokalen und Onlinebenutzern in Ihrem Unternehmen möglicherweise nicht erwartungsgemäß.           |
| Konfigurieren von Skype für hybride Business | Dies umfasst drei Schritte:  <br>1. konfigurieren Sie Ihrer lokalen Edge-Dienst für den Verbund mit Skype für Business Online. <br> 2. konfigurieren Sie Ihrer Skype für Business Online Mandanten für einen freigegebenen SIP-Adressraum. <br> 3. Konfigurieren der Authentifizierung bei Bedarf.    <br> Weitere Informationen finden Sie unter [Konfigurieren von Skype für hybride Business](configure-federation-with-skype-for-business-online.md).
|Verschieben von Pilotbenutzern  <br/> |Nachdem Sie die Schritte zum Vorbereiten und Konfigurieren der Umgebung für Skype für Business Online abgeschlossen haben, können Sie die Pilotbenutzer in Ihrem online Office 365-Mandanten verschieben starten. Weitere Informationen finden Sie unter [Verschieben von Benutzern aus lokal zu Skype für Business Online](move-users-from-on-premises-to-skype-for-business-online.md) und [Verschieben von Benutzern aus Teams lokal](move-users-from-on-premises-to-Teams.md).  <br/> | 

  