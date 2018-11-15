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
ms.openlocfilehash: 2f14859e600a06a57b67a14249e954f3e4e6d4a2
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531667"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Konfigurieren von hybridkonnektivität zwischen Skype für Business Server und Office 365
 
**Zusammenfassung:** Lesen Sie dieses Thema, um Informationen zum Konfigurieren von hybridkonnektivität zwischen Skype für Business Server und Teams oder Skype für Business Online.  Hybridkonnektivität können Sie Ihre lokalen Benutzer Teams oder Skype für Business Online verschieben, und ermöglicht es Benutzern Cloud-Dienste nutzen.
  
Bevor Sie die Schritte in diesem Thema ausführen, sollten Sie [Planen hybridkonnektivität zwischen Skype für Business Server und Office 365](plan-hybrid-connectivity.md)gelesen haben.
  
Die folgende Tabelle enthält die erforderlichen Aufgaben zum Konfigurieren von Skype für Business hybridkonnektivität und enthält Links zu verwandten Artikeln Weitere Informationen.
  
|**Schritt**|**Beschreibung**|
|:-----|:-----|
|Erstellen Sie ein Konto Mandanten für Office 365   <br/> |Informationen Sie zu Office 365 unter [Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Machen Sie sich mit den [Systemanforderungen](https://products.office.com/en-US/office-system-requirements) vertraut, um sicherzustellen, dass Ihre Umgebung für Office 365 bereit ist.  <br/> Einzelheiten zum Einrichten von Office 365 finden Sie unter [Erste Schritte mit Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Fügen Sie Ihrer Domäne zu Office 365-Mandanten hinzu und verifizieren Sie des Eigentums an  <br/> | Sie müssen Ihre Domäne dem Office 365-Mandanten hinzufügen und dann den Schritten zum Überprüfen der Domäne mit Office 365 folgen. Anhand dieser Schritte soll bestätigt werden, dass Sie der Besitzer der Domäne sind. <br/> Befolgen Sie die Schritte unter [Hinzufügen einer Domäne zu Office 365](https://support.office.com/en-us/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US), zum Hinzufügen Ihrer Domäne zu Office 365-Mandanten.  <br/> |
|Einrichten von Active Directory-Synchronisierung  <br/> |Active Directory-Synchronisierung vermeidet eine Verbindung zwischen Ihrer lokalen Active Directory ständig mit Office 365 synchronisiert. Hiermit können Sie synchronisierte Versionen der einzelnen Benutzerkonto und Gruppe erstellen.  <br/> <br> **Wichtig:** Sie müssen die Active Directory-Konten für alle Skype für Unternehmensbenutzer in Ihrer Organisation zwischen Ihrer lokalen und online-Bereitstellungen, synchronisieren, auch wenn der Benutzer nicht in Teams oder Skype für Business Online verschoben werden. Wenn Sie nicht alle Benutzer synchronisieren, funktioniert die Kommunikation zwischen lokalen und Onlinebenutzern in Ihrem Unternehmen möglicherweise nicht erwartungsgemäß. Weitere Informationen finden Sie unter [Konfigurieren von Azure Active Directory verbinden für hybridumgebungen](configure-azure-ad-connect.md).         |
| Konfigurieren von Skype für hybride Business | Es gibt drei grundlegende Schritte: <br><br> 1. konfigurieren Sie Ihrer lokalen Umgebung den Verbund mit Office 365. <br> 2. konfigurieren Sie Ihrer lokalen Umgebung zu Office 365-Vertrauensstellung und aktivieren Sie freigegebenen SIP-Adressraums mit Office 365.<br> 3. freigegebenen SIP-Adressraums in Ihrem Office 365-Mandanten zu aktivieren. <br><br> Darüber hinaus Wenn Sie lokale Exchange-Organisation haben, können dann Sie OAuth zwischen Ihrer Exchange lokal und Skype für Business Online-Umgebungen konfigurieren möchten. <br> <br>Weitere Informationen finden Sie unter [Konfigurieren von Skype für hybride Business](configure-federation-with-skype-for-business-online.md).
|Verschieben von Pilotbenutzern  <br/> |Nachdem Sie die Schritte zum Vorbereiten und Konfigurieren der Umgebung für Teams oder Skype für Business Online abgeschlossen haben, können Sie die Pilotbenutzer in Ihrem online Office 365-Mandanten verschieben starten. Weitere Informationen finden Sie unter [Verschieben von Benutzern aus lokal zu Skype für Business Online](move-users-from-on-premises-to-skype-for-business-online.md) und [Verschieben von Benutzern aus Teams lokal](move-users-from-on-premises-to-Teams.md).  <br/> | 

  