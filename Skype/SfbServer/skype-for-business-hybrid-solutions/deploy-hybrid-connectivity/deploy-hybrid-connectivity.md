---
title: Bereitstellen von Hybrid-Anbindung zwischen Skype for Business Server und Skype for Business Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
description: 'Zusammenfassung: Lesen Sie dieses Thema und erfahren Sie, wie Hybrid-Anbindung zwischen Skype for Business Server und Skype for Business Online hergestellt wird.'
ms.openlocfilehash: 1e42b0c582f186b785db691e66b9ee88aa6d6a74
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886196"
---
# <a name="deploy-hybrid-connectivity-between-skype-for-business-server-and-skype-for-business-online"></a>Bereitstellen von Hybrid-Anbindung zwischen Skype for Business Server und Skype for Business Online
 
**Zusammenfassung:** Lesen Sie dieses Thema und erfahren Sie, wie Hybrid-Anbindung zwischen Skype for Business Server und Skype for Business Online hergestellt wird.
  
Bevor Sie die Schritte in diesem Thema ausführen, sollten Sie [Planen hybridkonnektivität zwischen Skype für Business Server und Skype für Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)gelesen haben.
  
Hybridkonnektivität zwischen Skype für Business Server und Skype für Business Online bedeutet, dass Benutzer einer Domäne, z. B. "contoso.com", zwischen der Verwendung von Skype für Business Server lokal und Skype für Business Online verteilt sind. Einige der Domänenbenutzer werden lokal verwaltet, andere dagegen online. 
  
Die folgende Tabelle enthält die erforderlichen Schritte zur Vorbereitung Ihrer Umgebung für eine hybridbereitstellung mit Skype Business Online und Microsoft Office 365. 
  
|**Schritt**|**Beschreibung**|
|:-----|:-----|
|Erstellen Sie ein Konto Mandanten für Office 365 und aktivieren Skype für Business Online  <br/> |Informationen Sie zu Office 365 und Skype für Business Online unter [Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Um sicherzustellen, dass Ihre Umgebung für Office 365 bereit ist, finden Sie unter [System Requirements](https://products.office.com/en-US/office-system-requirements).  <br/> Ausführliche Informationen zum Einrichten von Office 365 finden Sie unter [Erste Schritte mit Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Fügen Sie Ihrer Domäne zu Office 365-Mandanten hinzu und verifizieren Sie des Eigentums an  <br/> | Sie müssen Ihre Domäne dem Office 365-Mandanten hinzufügen und dann den Schritten zum Überprüfen der Domäne mit Office 365 folgen. Anhand dieser Schritte soll bestätigt werden, dass Sie der Besitzer der Domäne sind. <br/> Befolgen Sie die Schritte unter [Hinzufügen Ihrer Domäne zu Office 365](https://support.office.com/en-us/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US), zum Hinzufügen Ihrer Domäne zu Office 365-Mandanten.  <br/> |
|Vorbereiten der Active Directory-Synchronisierung  <br/> |Active Directory-Synchronisierung vermeidet eine Verbindung zwischen Ihrer lokalen Active Directory ständig mit Office 365 synchronisiert. Hiermit können Sie erstellte synchronisiert Versionen der einzelnen Benutzerkonto und der Gruppe, und auch ermöglicht globale adresslist (GAL) Synchronisierung aus Ihrer lokalen Microsoft Exchange Server-Umgebung zu Microsoft Exchange Online verwendet. Weitere Informationen finden Sie unter [Directory Integration Tools](https://go.microsoft.com/fwlink/p/?LinkId=530320).  <br/>  **Wichtig** Sie müssen die Active Directory-Konten für alle Skype für Unternehmensbenutzer in Ihrer Organisation zwischen Ihrer lokalen und online-Bereitstellungen, synchronisieren, auch wenn der Benutzer nicht in Skype für Business Online verschoben werden. Wenn Sie nicht alle Benutzer synchronisieren, funktioniert die Kommunikation zwischen lokalen und Onlinebenutzern in Ihrem Unternehmen möglicherweise nicht erwartungsgemäß.           |
|Verschieben von Pilotbenutzern  <br/> |Nachdem Sie die Schritte zum Vorbereiten und Konfigurieren der Umgebung für Skype für Business Online abgeschlossen haben, können Sie die Pilotbenutzer in Ihrem online Office 365-Mandanten verschieben starten. Finden Sie unter [Verschieben von Benutzern aus lokal zu Skype für Business Online](move-users-from-on-premises-to-skype-for-business-online.md).  <br/> |
