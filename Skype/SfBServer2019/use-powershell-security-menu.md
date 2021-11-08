---
title: Verwenden von PowerShell für Aufgaben im Menü "Sicherheit"
ms.reviewer: ''
ms.author: ankum
author: ankum
manager: ravrao
ms.date: 11/03/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: 'Zusammenfassung: Skype for Business Server Systemsteuerung zur Cmdlet-Zuordnung für Die Sicherheit.'
ms.openlocfilehash: 6e726b13b9428b213011126abf5ac0869e6cfbf8
ms.sourcegitcommit: eba9fc680233e9e03773a2942f22afe6247eec41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60824932"
---
# <a name="security"></a>Sicherheit

In diesem Artikel wird beschrieben, wie ähnliche Ergebnisse wie die des Menüelements **"Sicherheit"** in der älteren Systemsteuerung mithilfe von Cmdlets erzielt werden können.

In diesem Artikel werden die folgenden Untermenüs beschrieben:

- [Sicherheit](#security)
  - [Registrar](#registrar)
  - [Webdienst](#web-service)
  - [PIN-Richtlinie](#pin-policy)

## <a name="registrar"></a>Registrar

Im Untermenü **"REGISTRAR"** können Administratoren Proxyserver über Proxyserverkonfigurationseinstellungen verwalten. Mit diesen Einstellungen, die sowohl auf globaler als auch auf Dienstebene angewendet werden können (nur für edgeserver- und Registrierungsstellendienste), können Sie z. B. die Authentifizierungsprotokolle steuern, die von Clientendpunkten verwendet werden können, und steuern, ob die Komprimierung für eingehende und ausgehende Proxyserververbindungen verwendet wird.

Betrachten wir die verschiedenen Aufgaben, die ein Benutzer für **REGISTRAR** ausführen kann, und die Skype for Business Cmdlets, denen diese Aufgaben zugeordnet sind.

---

> **Szenario 1:** Auflisten aller Proxykonfigurationen

   ![Proxykonfiguration auflisten](./media/proxy-configurations-1.png)

***Cmdlet***

[Get-CsProxyConfiguration](/powershell/module/skype/get-csproxyconfiguration)

***Beispiel***

```powershell
 Get-CsProxyConfiguration
```

---

> **Szenario 2:** Erstellen einer neuen Proxykonfiguration

   ![Proxykonfiguration erstellen](./media/proxy-configurations-2.png)

***Cmdlet***

[New-CsProxyConfiguration](/powershell/module/skype/new-csproxyconfiguration)  

***Beispiel***

```powershell
 New-CsProxyConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -RequestServerCompression $True -MaxClientMessageBodySizeKb 256
```

---

> **Szenario 3:** Abrufen von Details zu einer ausgewählten Proxykonfiguration

   ![Proxykonfiguration abrufen](./media/proxy-configurations-3.png)

***Cmdlet***

[Get-CsProxyConfiguration](/powershell/module/skype/get-csproxyconfiguration)

***Beispiel***

```powershell
 Get-CsProxyConfiguration -Identity "service:EdgeServer:atl-cs-001.litwareinc.com"
```

---

> **Szenario 4:** Löschen ausgewählter Proxykonfigurationen

   ![Proxykonfiguration löschen](./media/proxy-configurations-4.png)

***Cmdlet***

[Remove-CsProxyConfiguration](/powershell/module/skype/remove-csproxyconfiguration)

***Beispiel***

```powershell
 Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
```

---

> **Szenario 5:** Aktualisieren einer Proxykonfiguration

   ![Proxykonfiguration aktualisieren](./media/proxy-configurations-5.png)

***Cmdlet***

[Set-CsProxyConfiguration](/powershell/module/skype/set-csproxyconfiguration)

***Beispiel***

```powershell
 Set-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-001.litwareinc.com -AcceptServerCompression $True
```

---

## <a name="web-service"></a>Webdienst

Das  Web SERVICE-Untermenüelement unter **"Sicherheit"** ermöglicht Administratoren die Verwaltung von Konfigurationseinstellungen für Webdienste in der gesamten Organisation. Dazu gehören die Verwaltung der Gruppenerweiterung, Zertifikateinstellungen und zulässigen Authentifizierungsmethoden. Da Administratoren unterschiedliche Einstellungen auf globaler, Standort- und Dienstebene konfigurieren können (allerdings nur für den Webdienstdienst), können Webdienstfunktionen für unterschiedliche Benutzer und unterschiedliche Speicherorte angepasst werden.

Betrachten wir die verschiedenen Aufgaben, die ein Benutzer in **WEB SERVICE** ausführen kann, und die Skype for Business Cmdlets, denen diese Aufgaben zugeordnet sind.

---
> **Szenario 1:** Auflisten aller Webdienstkonfigurationen

   ![Webdienstkonfiguration auflisten](./media/web-service-1.png)

***Cmdlet***

[Get-CsWebServiceConfiguration](/powershell/module/skype/get-cswebserviceconfiguration)

***Beispiel***

```powershell
 Get-CsWebServiceConfiguration
```

---

> **Szenario 2:** Erstellen einer neuen Webdienstkonfiguration

   ![Neue Webdienstkonfiguration](./media/web-service-2.png)

***Cmdlet***

[New-CsWebServiceConfiguration](/powershell/module/skype/new-cswebserviceconfiguration)  

***Beispiel***

```powershell
 New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True
```

---

> **Szenario 3:** Abrufen von Details zu einer ausgewählten Webdienstkonfiguration

   ![Webdienstkonfiguration abrufen](./media/web-service-3.png)

***Cmdlet***

[Get-CsWebServiceConfiguration](/powershell/module/skype/get-cswebserviceconfiguration)

***Beispiel***

```powershell
 Get-CsWebServiceConfiguration -Identity site:Redmond
```

---

> **Szenario 4:** Ausgewählte Webdienstkonfigurationen löschen

   ![Löschen der Webdienstkonfiguration](./media/web-service-4.png)

***Cmdlet***

[Remove-CsWebServiceConfiguration](/powershell/module/skype/remove-cswebserviceconfiguration)

***Beispiel***

```powershell
 Remove-CsWebServiceConfiguration -Identity site:Redmond
```

---

> **Szenario 5:** Aktualisieren einer Webdienstkonfiguration

   ![Aktualisieren der Webdienstkonfiguration](./media/Web-service-5.png)

***Cmdlet***

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration)

***Beispiel***

```powershell
 Set-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $True
```

---

## <a name="pin-policy"></a>PIN-Richtlinie

Administratoren können **PIN POLICY** verwenden, um PIN-Authentifizierungseigenschaften zu verwalten. Beispielsweise kann die Mindestlänge für eine PIN angegeben und bestimmt werden, ob PINs zulässig sind, die "allgemeine Muster" verwenden, z. B. aufeinander folgende Ziffern (z. B. eine PIN wie 123456).

Betrachten wir die verschiedenen Aufgaben, die ein Benutzer mit **PIN POLICY** ausführen kann, und die Skype for Business Cmdlets, denen diese Aufgaben zugeordnet sind.

---

> **Szenario 1:** Auflisten aller PIN-Richtlinien

   ![Pin-Richtlinie auflisten](./media/pin-policy-1.png)

***Cmdlet***

[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy)

***Beispiel***

```powershell
 Get-CsPinPolicy
```

---

> **Szenario 2:** Erstellen einer neuen PIN-Richtlinie

   ![Pin-Richtlinie erstellen](./media/pin-policy-2.png)

***Cmdlet***

[New-CsPinPolicy](/powershell/module/skype/new-cspinpolicy)  

***Beispiel***

```powershell
 New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 10
```

---

> **Szenario 3:** Abrufen von Details zu einer ausgewählten PIN-Richtlinie

   ![PIN-Richtlinie abrufen](./media/pin-policy-3.png)

***Cmdlet***

[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy)

***Beispiel***

```powershell
 Get-CsPinPolicy -Identity "site:Redmond"
```

---

> **Szenario 4:** Löschen ausgewählter PIN-Richtlinien

   ![LÖSCHEN DER PIN-Richtlinie](./media/pin-policy-4.png)

***Cmdlet***

[Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy)

***Beispiel***

```powershell
 Remove-CsPinPolicy -Identity RedmondUsersPinPolicy
```

---

> **Szenario 5:** Aktualisieren einer PIN-Richtlinie

   ![Aktualisieren der PIN-Richtlinie](./media/pin-policy-5.png)

***Cmdlet***

[Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy)

***Beispiel***

```powershell
 Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

---
