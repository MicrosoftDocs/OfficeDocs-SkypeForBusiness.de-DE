---
title: Export-CcRootCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: Das Cmdlet Export-CcRootCertificate exportiert das Zertifikat der Stammzertifizierungsstelle in eine lokale Datei auf dem Skype for Business Cloud Connector Edition Hostserver.
ms.openlocfilehash: e00041088af39bf6f11abd5309ff293bd37bf38f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624997"
---
# <a name="export-ccrootcertificate"></a>Export-CcRootCertificate
 
Das Cmdlet Export-CcRootCertificate exportiert das Zertifikat der Stammzertifizierungsstelle in eine lokale Datei auf dem Skype for Business Cloud Connector Edition Hostserver. 
  
```powershell
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird der Parameter "Path" als Verzeichnispfad und nicht als Dateipfad festgelegt. Es generiert die Datei c:\test\CCERootCertificates.p7b.
  
```powershell
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Mit dem Cmdlet Export-CcRootCertificate können Sie die Stamm- und Zwischenzertifikate in einem Dateipfad speichern. Dies kann bei einem Notfallwiederherstellungsszenario hilfreich sein. 
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|Pfad  <br/> |Erforderlich  <br/> |System.String  <br/> |Dateipfad, in dem das Zertifikat gespeichert wird.  <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das cmdlet Export-CcRootCertificate akzeptiert keine weitergeleitete Eingabe. 
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

Keine
  

