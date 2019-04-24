---
title: Export-CcRootCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: 'Das Cmdlet „Export-CcRootCertificate“ exportiert das Zertifikat der Stammzertifizierungsstelle in eine lokale Datei auf dem Hostserver von Skype for Business Cloud Connector Edition. '
ms.openlocfilehash: c2647baa9ab6762feb8f550e0d726b18ab5d3090
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233981"
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
| Path  <br/> |Erforderlich  <br/> |System.String  <br/> |Dateipfad, in dem das Zertifikat gespeichert wird   <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Export-CcRootCertificate“ akzeptiert keine Pipelineeingaben.  
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine 
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

Keine
  

