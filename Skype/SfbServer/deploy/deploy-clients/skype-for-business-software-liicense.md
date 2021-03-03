---
title: Skype Room System Skype for Business-Softwarelizenz
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: In diesem Thema erfahren Sie, wie Sie überprüfen können, ob Sie über eine Skype for Business-Softwarevolumelizenz verfügen.
ms.openlocfilehash: 20e04f69ba5a931bae6ac8598567165a7a6043a4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833925"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype Room System: Skype for Business-Softwarelizenz
 
In diesem Thema erfahren Sie, wie Sie überprüfen können, ob Sie über eine Skype for Business-Softwarevolumelizenz verfügen. 
  
Skype Room System verwendet einen installierten Skype for Business-Client, für den eine Softwarevolumelizenz erforderlich ist. Bevor Sie das erste Skype Room System bereitstellen, sollten Sie den Volumenlizenzstatus der Bereitstellung herausfinden – mithilfe von Schlüsselverwaltungsservern (Key Management Servers, KMS) oder mehrfachen Aktivierungsschlüsseln (Multiple Activation Keys, MAK).
  
## <a name="key-management-servers-kms"></a>Schlüsselverwaltungsserver (Key Management Servers, KMS)

Wenn KMS vorhanden ist und Skype for Business Volumenlizenzaktivierungen verteilt, aktiviert das Skype Room System automatisch den Skype for Business-Client. So finden Sie heraus, ob KMS bereits vor Ort ist:
  
Führen Sie an einer Eingabeaufforderung folgenden Befehl aus:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Weitere Informationen finden Sie unter Ermitteln von Office- und [Windows-KMS-Hosts über DNS und Entfernen nicht autorisierter Instanzen.](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx) 
  
Informationen zum Einrichten eines KMS finden Sie unter ["KMS-Aktivierung von Office 2013"](https://technet.microsoft.com/library/ee624357.aspx) und ["GVLKs" für die KMS-](https://technet.microsoft.com/library/dn385360.aspx) und Active Directory-Aktivierung von Office 2013.
  
Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (Dieser Schlüssel bewirkt, dass das Skype Room System im Netzwerk nach einem KMS sucht.)
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Mehrfachaktivierungsschlüssel (Multiple Activation Keys, MAK) aus dem Volume License Service Center (VLSC)

Wenn der Kunde eine andere Volumenlizenzsoftware verwendet, verwaltet die IT-Abteilung die Softwareaktivierungen und den Volumenlizenzvertrag (Volume License Agreement, VLA) mithilfe von VLSC. Dadurch kann das Unternehmen auch Skype for Business -VL-Aktivierungen erwerben, nach denen das Unternehmen einen MAK für die Eingabe in der Skype Room System Admin Console abrufen kann.
  
Ein Kunde mit einem VLA muss seine VLSC-Anmeldeinformationen kennen, die verwendet werden, um den Vertrag zu verwalten und mak zu erhalten. Wenn unsicher, sollte die Finanzabteilung des Kunden bestätigen können, ob der Kunde ein VLA bezahlt hat.
  
Um einen MAK zu erhalten, greifen Sie auf das Volume Licensing Service Center zu, um Verträge eins zu sehen und Product Keys (MAK) herunterzuladen. Weitere Informationen finden Sie im [Volume Licensing Service Center.](https://www.microsoft.com/Licensing/servicecenter/default.aspx) 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a>MAK für Microsoft 365 oder Office 365 ohne VLSC-Zugriff

Wenn der Kunde keinen Volumenlizenzvertrag besitzt, sind Skype for Business-Aktivierungen viel schwieriger zu verwalten. Microsoft 365- und Office 365-Kunden ohne VLSC-Zugriff können jedoch einen Werbe-MAK erhalten, indem sie dem OEM, der das Skype Room System verkauft, die folgenden Informationen bereitstellen:
  
- Firmenname
    
- Name, E-Mail-Adresse und Telefonnummer des Bereitstellungskontakts
    
- Anzahl der bereitgestellten Systeme
    
- Bereitstellungsdatum
    
- Wenn der Kunde über einen Microsoft Technical Account Manager verfügt, werden der Name und die Kontaktinformationen des TAM
    

