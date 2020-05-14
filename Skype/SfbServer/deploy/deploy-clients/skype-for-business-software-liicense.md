---
title: Skype Room System Skype for Business-Softwarelizenz
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Lesen Sie dieses Thema, um zu erfahren, wie Sie überprüfen können, ob Sie über eine Skype for Business Software Volumenlizenz verfügen.
ms.openlocfilehash: a44e95d8cd488e2b12e03ee9848ef3d1b254180c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220925"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype Room System: Skype for Business Softwarelizenz
 
Lesen Sie dieses Thema, um zu erfahren, wie Sie überprüfen können, ob Sie über eine Skype for Business Software Volumenlizenz verfügen. 
  
Skype Room System verwendet einen installierten Skype for Business-Client, für den eine Software Volumenlizenz erforderlich ist. Ermitteln Sie vor dem Bereitstellen des ersten Skype-Raumsystems den Volumenlizenz Status der Bereitstellung mithilfe von Schlüsselverwaltungsservern (KMS) oder mehrfachaktivierungsschlüsseln (MAK).
  
## <a name="key-management-servers-kms"></a>Schlüsselverwaltungsserver (KMS)

Wenn KMS vorhanden ist und Skype for Business Volumenlizenz Aktivierungen verteilen wird, aktiviert das Skype Room-System automatisch den Skype for Business-Client. So ermitteln Sie, ob KMS vorhanden ist:
  
Führen Sie an einer Eingabeaufforderung Folgendes aus:`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Weitere Informationen finden Sie unter [So ermitteln Sie Office-und Windows KMS-Hosts über DNS und Entfernen nicht autorisierter Instanzen](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx). 
  
Informationen zum Einrichten eines KMS finden Sie unter [KMS-Aktivierung von Office 2013](https://technet.microsoft.com/library/ee624357.aspx) und [GVLKs für KMS und Active Directory Aktivierung von Office 2013](https://technet.microsoft.com/library/dn385360.aspx)
  
Office 2013 generischer Volumenlizenzschlüssel für lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (dieser Schlüssel veranlasst das Skype Room-System, nach einem KMS im Netzwerk zu suchen.)
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Mehrfachaktivierungsschlüssel (MAK) aus dem Volume License Service Center (VLSC)

Wenn der Kunde eine andere Volumenlizenz Software verwendet, verwaltet die IT-Abteilung die Software Aktivierungen und den Volumenlizenz Vertrag (VLA) mithilfe der VLSC. Dadurch kann das Unternehmen auch Skype for Business VL-Aktivierungen erwerben, nach denen das Unternehmen einen MAK für die Eingabe in der Skype Room System-Verwaltungskonsole erhalten kann.
  
Ein Kunde mit Vla muss seine VLSC-Anmeldeinformationen kennen, die zur Verwaltung der Vereinbarung und zum Abrufen von MAK verwendet werden. Wenn die Finanzabteilung des Kunden unsicher ist, sollte Sie bestätigen können, wenn der Kunde eine Vla bezahlt hat.
  
Um einen MAK zu erhalten, greifen Sie auf das Volumen Lizenzierungs-Service Center zu, um Vereinbarungen anzuzeigen und Produktschlüssel (MAK) herunterzuladen. Weitere Informationen finden Sie im [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx). 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a>MAK für Microsoft 365 oder Office 365 ohne VLSC-Zugriff

Wenn der Kunde nicht über eine Volumenlizenzvereinbarung verfügt, ist die Verwaltung Skype for Business Aktivierungen wesentlich schwieriger. Microsoft 365 und Office 365 Kunden ohne VLSC-Zugriff können jedoch einen Promotions-MAK erhalten, indem Sie den OEM, der das Skype Room-System verkauft, folgende Informationen bereitstellen:
  
- Firma
    
- Bereitstellungs Kontakt Name, e-Mail und Telefonnummer
    
- Anzahl der bereitgestellten Systeme
    
- Bereitstellungsdatum
    
- Wenn der Kunde über einen technischen Microsoft Account Manager verfügt, werden der Name und die Kontaktinformationen des TAM
    

