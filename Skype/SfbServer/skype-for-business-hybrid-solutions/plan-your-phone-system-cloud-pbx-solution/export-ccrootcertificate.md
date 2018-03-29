---
title: Export-CcRootCertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: Das Cmdlet „Export-CcRootCertificate“ exportiert das Zertifikat der Stammzertifizierungsstelle in eine lokale Datei auf dem Hostserver von Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 9af3701fd89cf881b4f966c2b00500ad4e55bc9b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="export-ccrootcertificate"></a>Export-CcRootCertificate
 
Das Cmdlet „Export-CcRootCertificate“ exportiert das Zertifikat der Stammzertifizierungsstelle in eine lokale Datei auf dem Hostserver von Skype for Business Cloud Connector Edition. 
  
```
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird der „Path“-Parameter als Verzeichnispfad festgelegt, nicht als Dateipfad. Damit wird die Datei „c:\test\CCERootCertificates.p7b“ generiert.
  
```
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Mit dem Cmdlet „Export-CcRootCertificate“ können Sie die Stamm- und Zwischenzertifikate in einem Dateipfad speichern. Dies kann in Notfallwiederherstellungs-Szenarien hilfreich sein. 
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
| Path  <br/> |Erforderlich  <br/> |System.String  <br/> |Dateipfad, in dem das Zertifikat gespeichert wird  <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Export-CcRootCertificate“ akzeptiert keine Pipelineeingaben. 
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

Keine
  

