---
title: Skype-Raum System-Softwarelizenz für Skype for Business
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Lesen Sie dieses Thema und erfahren Sie, wie Sie überprüfen, ob Sie über eine Volumenlizenzierung für die Skype for Business-Software verfügen.
ms.openlocfilehash: 731eefa49714fdced552c6cbedf4ecc288065d6b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234723"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype Room System: Skype for Business-Softwarelizenz
 
Lesen Sie dieses Thema und erfahren Sie, wie Sie überprüfen, ob Sie über eine Volumenlizenzierung für die Skype for Business-Software verfügen. 
  
Skype Room System verwendet einen installierten Skype for Business-Client, für den eine Software-Volumenlizenz erforderlich ist. Informieren Sie sich vor der Bereitstellung des ersten Skype-Raumsystems über den Volumenlizenz Status der Bereitstellung-mithilfe von Schlüsselverwaltungsservern (KMS) oder mehrerer Aktivierungsschlüssel (MAK).
  
## <a name="key-management-servers-kms"></a>Schlüsselverwaltungsserver (KMS)

Wenn KMS vorhanden ist und die Aktivierung von Skype for Business-Volumenlizenzen vertreibt, wird der Skype for Business-Client automatisch vom Skype-Raum System aktiviert. So finden Sie heraus, ob KMS vorhanden sind:
  
Führen Sie an einer Eingabeaufforderung Folgendes aus:`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Weitere Informationen finden Sie unter [so wird es gemacht: Ermitteln von Office-und Windows KMS-Hosts über DNS und Entfernen nicht autorisierter Instanzen](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx). 
  
Informationen zum Einrichten eines KMS finden Sie unter [KMS-Aktivierung von Office 2013](https://technet.microsoft.com/library/ee624357.aspx) und [GVLKs für KMS und Active Directory-Aktivierung von Office 2013](https://technet.microsoft.com/library/dn385360.aspx)
  
Office 2013 Generic Volume License Key für lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (dieser Schlüssel bewirkt, dass das Skype-Raum System nach einem KMS im Netzwerk sucht).
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Mehrfachaktivierungsschlüssel (MAK) aus dem Volume License Service Center (VLSC)

Wenn der Kunde eine andere Volumenlizenz Software verwendet, verwaltet die IT-Abteilung die Software Aktivierungen und den Volumenlizenz Vertrag (VLA) mit dem VLSC. Auf diese Weise kann das Unternehmen auch Skype for Business-VL-Aktivierungen erwerben, nach denen das Unternehmen einen MAK für die Eingabe in die Skype Room-System Administratorkonsole erhalten kann.
  
Ein Kunde mit einem Vla muss seine VLSC-Anmeldeinformationen kennen, die verwendet werden, um den Vertrag zu verwalten und MAK zu erhalten. Wenn Sie unsicher sind, sollte die Finanzabteilung des Kunden bestätigen können, ob der Kunde eine Vla bezahlt hat.
  
Greifen Sie, um einen MAK zu beziehen, auf das Volume Licensing Service Center zu, um die Vereinbarungen anzeigen zu lassen und um Produktschlüssel (MAK) herunterzuladen. Weitere Informationen finden Sie im [Volumen Lizenzierungs-Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx). 
  
## <a name="mak-for-office-365-without-vlsc-access"></a>MAK für Office 365 ohne VLSC-Zugriff

Wenn der Kunde keine VolumenLizenzvereinbarung hat, ist die Verwaltung von Skype for Business-Aktivierungen wesentlich schwieriger. Office 365-Kunden ohne VLSC-Zugriff können jedoch ein Werbe-MAK erhalten, indem Sie dem OEM, der das Skype-Raum System verkauft, die folgenden Informationen zur Verfügung stellen:
  
- Name des Unternehmens
    
- Name, E-Mail-Adresse und Telefonnummer des Kontakts für die Bereitstellung
    
- Anzahl der bereitgestellten Systeme
    
- Bereitstellungsdatum
    
- Wenn der Kunde über einen Microsoft Technical Account Manager verfügt, Name und Kontaktinformationen des TAM
    

