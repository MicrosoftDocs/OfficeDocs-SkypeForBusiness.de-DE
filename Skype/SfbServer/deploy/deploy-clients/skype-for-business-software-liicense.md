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
description: In diesem Thema erfahren Sie, wie Sie überprüfen, ob Sie über eine Skype for Business-Softwarevolumelizenz verfügen.
ms.openlocfilehash: 40b72e39fc0edc23b4cc0d17f82ba633c2ac24af
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113091"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype Room System: Skype for Business-Softwarelizenz
 
In diesem Thema erfahren Sie, wie Sie überprüfen, ob Sie über eine Skype for Business-Softwarevolumelizenz verfügen. 
  
Skype Room System verwendet einen installierten Skype for Business-Client, der eine Softwarevolumelizenz erfordert. Informieren Sie sich vor der Bereitstellung des ersten Skype Room Systems über den Volumenlizenzstatus der Bereitstellung – mithilfe von Schlüsselverwaltungsservern (Key Management Servers, KMS) oder mehreren Aktivierungsschlüsseln (Multiple Activation Keys, MAK).
  
## <a name="key-management-servers-kms"></a>Schlüsselverwaltungsserver (Key Management Servers, KMS)

Wenn KMS vorhanden ist und Skype for Business Volumenlizenzaktivierungen verteilt, aktiviert das Skype Room System automatisch den Skype for Business-Client. So finden Sie heraus, ob KMS an Ort und Stelle ist:
  
Führen Sie an einer Eingabeaufforderung aus:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Weitere Informationen finden Sie unter Ermitteln von Office- und [Windows -KMS-Hosts](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx)über DNS und Entfernen nicht autorisierter Instanzen . 
  
Informationen zum Einrichten eines KMS finden Sie unter [KMS-Aktivierung von Office 2013](/previous-versions/office/office-2013-resource-kit/ee624357(v=office.15)) und [GVLKs für KMS und Active Directory-Aktivierung von Office 2013](/DeployOffice/vlactivation/gvlks)
  
Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (Dieser Schlüssel bewirkt, dass das Skype Room System nach einem KMS im Netzwerk sucht.)
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Multiple Activation Keys (MAK) aus dem Volume License Service Center (VLSC)

Wenn der Kunde eine andere Volumenlizenzsoftware verwendet, verwaltet die IT-Abteilung die Softwareaktivierungen und den Volumenlizenzvertrag (Volume License Agreement, VLA) mithilfe des VLSC. Dadurch kann das Unternehmen auch Skype for Business-VL-Aktivierungen erwerben, nach denen das Unternehmen einen MAK für die Eingabe in der Skype Room System Admin Console abrufen kann.
  
Ein Kunde mit einem VLA muss seine VLSC-Anmeldeinformationen kennen, die verwendet werden, um den Vertrag zu verwalten und mak zu erhalten. Wenn unsicher, sollte die Finanzabteilung des Kunden in der Lage sein, zu bestätigen, ob der Kunde ein VLA bezahlt hat.
  
Um einen Mak zu erhalten, greifen Sie auf das Volume Licensing Service Center zu, um Vereinbarungen eins zu sehen und Product Keys (MAK) herunterzuladen. Weitere Informationen finden Sie im [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx). 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a>MAK für Microsoft 365 oder Office 365 ohne VLSC-Zugriff

Wenn der Kunde keinen Volumenlizenzvertrag besitzt, sind Skype for Business-Aktivierungen wesentlich schwieriger zu verwalten. Microsoft 365- und Office 365-Kunden ohne VLSC-Zugriff können jedoch einen Werbe-MAK erhalten, indem sie dem OEM, der das Skype Room System verkauft, die folgenden Informationen bereitstellen:
  
- Firmenname
    
- Name, E-Mail und Telefonnummer der Bereitstellung
    
- Anzahl der bereitgestellten Systeme
    
- Bereitstellungsdatum
    
- Wenn der Kunde über einen Microsoft Technical Account Manager verfügt, werden der Name und die Kontaktinformationen des TAM
