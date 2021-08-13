---
title: Skype Softwarelizenz für Raumsystem Skype for Business
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
description: Lesen Sie dieses Thema, um zu erfahren, wie Sie überprüfen, ob Sie über eine Skype for Business Softwarevolumelizenz verfügen.
ms.openlocfilehash: c1294df980a1fca2118e6ca2e9b172904365639900081fad7425b4d850501fdc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54297611"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype Room System: Skype for Business-Softwarelizenz
 
Lesen Sie dieses Thema, um zu erfahren, wie Sie überprüfen, ob Sie über eine Skype for Business Softwarevolumelizenz verfügen. 
  
Skype Room System verwendet einen installierten Skype for Business-Client, für den eine Softwarevolumelizenz erforderlich ist. Bevor Sie die erste Skype Raumsystem bereitstellen, sollten Sie den Volumenlizenzstatus der Bereitstellung ermitteln – mithilfe von Schlüsselverwaltungsservern (KMS) oder mehreren Aktivierungsschlüsseln (Multiple Activation Keys, MAK).
  
## <a name="key-management-servers-kms"></a>Schlüsselverwaltungsserver (KMS)

Wenn KMS vorhanden sind und Skype for Business Volumenlizenzaktivierungen verteilen, aktiviert das Skype Raumsystem automatisch den Skype for Business Client. So ermitteln Sie, ob KMS vorhanden sind:
  
Führen Sie an einer Eingabeaufforderung Folgendes aus:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Weitere Informationen finden Sie unter [Ermitteln Office und Windows KMS Hosts über DNS und Entfernen nicht autorisierter Instanzen.](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx) 
  
Informationen zum Einrichten einer KMS finden Sie unter [KMS Aktivierung von Office 2013](/previous-versions/office/office-2013-resource-kit/ee624357(v=office.15)) und [GVLKs für KMS und Active Directory-Aktivierung von Office 2013](/DeployOffice/vlactivation/gvlks)
  
Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (Dieser Schlüssel bewirkt, dass das Skype Room System nach einem KMS im Netzwerk sucht.)
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Mehrere Aktivierungsschlüssel (MAK) aus dem Volume License Service Center (VLSC)

Wenn der Kunde eine andere Volumenlizenzsoftware verwendet, verwaltet die IT-Abteilung die Softwareaktivierungen und den Volumenlizenzvertrag (Volume License Agreement, VLA) mithilfe der VLSC. Dadurch kann das Unternehmen auch Skype for Business VL-Aktivierungen erwerben, nach denen das Unternehmen einen MAK zur Eingabe in der Skype Room System Admin Console erhalten kann.
  
Ein Kunde mit einem VLA muss seine VLSC-Anmeldeinformationen kennen, die verwendet werden, um den Vertrag zu verwalten und MAK zu erhalten. Wenn unsicher, sollte die Finanzabteilung des Kunden bestätigen können, ob der Kunde ein VLA bezahlt hat.
  
Um einen MAK zu erhalten, greifen Sie auf das Volume Licensing Service Center zu, um Vereinbarungen anzuzeigen und Product Keys (MAK) herunterzuladen. Weitere Informationen hierzu können Sie im [Volume Licensing Service Center abrufen.](https://www.microsoft.com/Licensing/servicecenter/default.aspx) 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a>MAK für Microsoft 365 oder Office 365 ohne VLSC-Zugriff

Wenn der Kunde über keinen Volumenlizenzvertrag verfügt, sind Skype for Business Aktivierungen viel schwieriger zu verwalten. Microsoft 365 und Office 365 Kunden ohne VLSC-Zugriff können jedoch einen Werbe-MAK erhalten, indem sie dem OEM, der das Skype Room System verkauft, die folgenden Informationen zur Verfügung stellen:
  
- Firmenname
    
- Bereitstellungskontaktname, E-Mail und Telefonnummer
    
- Anzahl der bereitgestellten Systeme
    
- Bereitstellungsdatum
    
- Wenn der Kunde über einen Microsoft Technical Account Manager verfügt, werden der Name und die Kontaktinformationen des TAM
