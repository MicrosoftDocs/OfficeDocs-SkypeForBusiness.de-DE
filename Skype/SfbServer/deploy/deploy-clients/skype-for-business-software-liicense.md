---
title: Skype Raum System Skype für Business-Lizenz
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Lesen Sie dieses Thema und erfahren Sie, wie Sie überprüfen, ob Sie über eine Volumenlizenzierung für die Skype for Business-Software verfügen.
ms.openlocfilehash: 8bc8abfb4b379faaf94ac8cf8fbf4fdb792329bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893346"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype Room System: Skype for Business-Softwarelizenz
 
Lesen Sie dieses Thema und erfahren Sie, wie Sie überprüfen, ob Sie über eine Volumenlizenzierung für die Skype for Business-Software verfügen. 
  
Skype Raum System verwendet eine installierte Skype für Business-Client, die eine Volumenlizenz Software erforderlich sind. Erfahren Sie vor der Bereitstellung von der ersten Skype Raum System, das Volume Lizenzstatus der Bereitstellung - Key Management Server (KMS) oder Mehrfachaktivierungsschlüssel (Multiple Activation Schlüssel, MAK) verwenden.
  
## <a name="key-management-servers-kms"></a>Schlüsselverwaltungsserver (KMS)

Wenn KMS vorhanden sind und Skype für Business Volume License Aktivierungen verteilt, wird das Skype Raum System automatisch die Skype für Business-Client aktiviert. So finden Sie heraus, ob KMS vorhanden sind:
  
Führen Sie an der Eingabeaufforderung aus:`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Weitere Informationen finden Sie unter [Office und Windows-KMS-Hosts über DNS-Ermittlung und Entfernen von nicht autorisierten Instanzen](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx). 
  
Informationen zum Einrichten eines KMS finden Sie unter [KMS-Aktivierung von Office 2013](https://technet.microsoft.com/library/ee624357.aspx) und [GVLKs für die KMS- und Active Directory-Aktivierung von Office 2013](https://technet.microsoft.com/library/dn385360.aspx)
  
Office 2013 Generic Volume License Product Key für Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (dieser Schlüssel wird das Skype Raum System für ein KMS im Netzwerk zu suchen.)
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Mehrfachaktivierungsschlüssel (MAK) aus dem Volume License Service Center (VLSC)

Wenn der Kunde anderen Volume License Software verwendet wird, wird die IT-Abteilung die Software Aktivierungen und Volume License Vereinbarung (VLA) mit der VLSC verwalten. Dadurch können auch das Unternehmen Skype für Business VL-Aktivierungen erwerben nach dem das Unternehmen einen MAK für die Eingabe in der Verwaltungskonsole von Skype Raum System erhalten kann.
  
Ein Kunde mit einer VLA muss ihre Anmeldeinformationen VLSC wissen, welche die zum Verwalten der Vereinbarung und Abrufen von MAK verwendet wird. Wenn Sie nicht sicher sind, sollte der Kunde Finanzabteilung können Sie überprüfen, wenn der Kunde einen VLA gezahlt haben.
  
Greifen Sie, um einen MAK zu beziehen, auf das Volume Licensing Service Center zu, um die Vereinbarungen anzeigen zu lassen und um Produktschlüssel (MAK) herunterzuladen. Weitere Informationen finden Sie im [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx). 
  
## <a name="mak-for-office-365-without-vlsc-access"></a>MAK für Office 365 ohne VLSC-Zugriff

Wenn der Kunde einen Volumenlizenzvertrag besitzt, können Skype für Business Aktivierungen schwieriger zu verwalten. Jedoch können Office 365-Kunden ohne VLSC Zugriff einen Werbe MAK anfordern, indem er die folgende Informationen an dem OEM verkaufen Skype Raum System:
  
- Name des Unternehmens
    
- Name, E-Mail-Adresse und Telefonnummer des Kontakts für die Bereitstellung
    
- Anzahl der Systeme bereitgestellt
    
- Bereitstellungsdatum
    
- Wenn der Kunde einen Microsoft Technical Account Manager, des TAM Namen und Kontaktinformationen
    

