---
title: Erstellen von DNS-Einträgen für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 798a663c-0b63-4f75-b0a3-9c553cef8c5f
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie DNS konfigurieren und DNS-Einträge für eine Installation von Skype for Business Server erstellen. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverCenter unter: herunter.'
ms.openlocfilehash: b5b36ffb55077e20a4c7a70c7e086c5596673f9f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306647"
---
# <a name="create-dns-records-for-skype-for-business-server"></a>Erstellen von DNS-Einträgen für Skype for Business Server
 
**Zusammenfassung:** Informationen zum Konfigurieren von DNS und zum Erstellen von DNS-Einträgen für eine Installation von Skype for Business Server. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)Center unter: herunter.
  
Damit Skype for Business Server ordnungsgemäß funktioniert, müssen eine Reihe von DNS-Einstellungen (Domain Name System) vorhanden sein. Diese steuern den Zugriff der Clients auf die Dienste und sorgen dafür, dass die Server übereinander informiert sind. Diese Einstellungen müssen pro Bereitstellung nur einmal festgelegt werden, da ein einmal zugeordneter DNS-Eintrag domänenübergreifend zur Verfügung steht. Sie können die Schritte 1 bis 5 in einer beliebigen Reihenfolge ausführen. Die Schritte 6, 7 und 8 müssen jedoch wie in der Abbildung dargestellt nacheinander und nach den Schritten 1 bis 5 erfolgen. Die Erstellung von DNS-Einträgen wird in Schritt 5 beschrieben. Weitere Informationen zum Planen von DNS finden Sie unter [Umgebungsanforderungen für Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) -oder [Server Anforderungen für Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
> [!IMPORTANT]
> Es wird ausdrücklich darauf hingewiesen, dass es sich hier lediglich um ein Beispiel für die Erstellung von DNS-Einträgen in einer Windows-DNS-Umgebung handelt. Es gibt viele andere DNS-Einträge, die für Skype for Business Server erforderlich sind, und das Verfahren zum Erstellen von DNS-Einträgen hängt von dem System ab, das Sie zum Verwalten von DNS in Ihrer Organisation verwenden. Eine vollständige Liste der Anforderungen für DNS finden Sie unter [DNS-Anforderungen für Skype for Business Server](../../plan-your-deployment/network-requirements/dns.md). 
  
![Übersichtsdiagramm](../../media/d2fc733c-6a80-4d17-a02f-93b8c4bfb999.png)
  
## <a name="configure-dns"></a>Konfigurieren von DNS

Für Skype for Business Server sind DNS-Einträge erforderlich, damit Sie ordnungsgemäß funktionieren und für Benutzer zugänglich sind.
  
Das vorliegende Beispiel ist der Pool „contoso.local“ mit DNS-Lastenausgleich und einem FQDN. Dieser Pool besteht aus drei Servern mit Skype for Business Server Enterprise Edition. Ein Front-End-Server der Standard Edition kann nur einen einzelnen Server enthalten. Bei Verwendung der Standard Edition würden Sie nur den vollqualifizierten Domänennamen (FQDN) des einzelnen Standard Edition-Servers verwenden, wenn Sie auf die Front-End-Rolle verweisen und keinen Serverpool mit DNS-Lastenausgleich wie im gezeigten Beispiel erstellen. Dieses einfache Beispiel verwendet nur die Front-End-Rolle und umfasst die in der Tabelle unten aufgeführten DNS-Einträge. Informationen zum Planen Ihrer spezifischen DNS-Anforderungen finden Sie unter [DNS-Anforderungen für Skype for Business Server](../../plan-your-deployment/network-requirements/dns.md). 
  
 
|**Beschreibung**|**Eintragstyp**|**Name**|**Auflösung in**|**Lastenausgleichstyp**|
|:-----|:-----|:-----|:-----|:-----|
|Interner Webdienst-FQDN  <br/> |A  <br/> |webint.contoso.local  <br/> |VIP für interne Webdienste  <br/> |Unterstützte Software und Hardware  <br/> |
|Pool-FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |IP-Adresse von Server SFB01  <br/> |DNS  <br/> |
|FQDN von SFB01  <br/> |A  <br/> |SFB01.contoso.local  <br/> |IP-Adresse von Server SFB01  <br/> |DNS  <br/> |
|Pool-FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |IP-Adresse von Server SFB02  <br/> |DNS  <br/> |
|FQDN von SFB02  <br/> |A  <br/> |SFB02.contoso.local  <br/> |IP-Adresse von Server SFB02  <br/> |DNS  <br/> |
|Pool-FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |IP-Adresse von Server SFB03  <br/> |DNS  <br/> |
|FQDN von SFB03  <br/> |A  <br/> |SFB03.contoso.local  <br/> |IP-Adresse von Server SFB03  <br/> |DNS  <br/> |
|Skype for Business-AutoErmittlung  <br/> |A  <br/> |lyncdiscoverinternal.contoso.local  <br/> |VIP für interne Webdienste  <br/> |Unterstützte Software und Hardware  <br/> |
|Einfache URL für Besprechungen  <br/> |A  <br/> |meet.contoso.local  <br/> |VIP für interne Webdienste  <br/> |Unterstützte Software und Hardware  <br/> |
|Einfache URL vom Typ „Dialin“  <br/> |A  <br/> |dialin.contoso.local  <br/> |VIP für interne Webdienste  <br/> |Unterstützte Software und Hardware  <br/> |
|Einfache URL für Web Scheduler  <br/> |A  <br/> |scheduler.contoso.local  <br/> |VIP für interne Webdienste  <br/> |Unterstützte Software und Hardware  <br/> |
|Einfache URL für die Verwaltung  <br/> |A  <br/> |admin.contoso.local  <br/> |VIP für interne Webdienste  <br/> |Unterstützte Software und Hardware  <br/> |
|Vorgänger-Ermittlung  <br/> |SRV  <br/> |_sipinternaltls._tcp.contoso.local  <br/> |Pool-FQDN (Port 5061)  <br/> |-  <br/> |
   
### <a name="create-dns-records"></a>Erstellen von DNS-Einträgen

1. Melden Sie sich beim DNS-Server an und öffnen Sie **Server-Manager**.
    
2. Klicken Sie auf das Dropdownmenü **Extras** und dann auf **DNS**.
    
3. Erweitern Sie in der Konsolenstruktur für Ihre SIP-Domäne **Forward-Lookupzonen**, und erweitern Sie dann die SIP-Domäne, in der Skype for Business Server installiert wird.
    
4. Klicken Sie mit der rechten Maustaste auf die SIP-Domäne und wählen Sie **Neuer Host (A oder AAAA)** (siehe Abbildung).
    
     ![Neuen A-Eintrag auswählen](../../media/f89c5c1f-b5b7-428c-a6e3-2bcd12e878c3.png)
  
5. Geben Sie im Feld **Name** den Namen des Hosteintrags ein (der Domänenname wird automatisch angehängt).
    
6. Geben Sie im Feld **IP-Adresse** die IP-Adresse des einzelnen Front-End-Servers ein und wählen Sie dann **Verknüpften PTR-Eintrag erstellen** oder nach Bedarf **Authentifizierte Benutzer können DNS-Einträge mit demselben Besitzernamen aktualisieren**. Hierbei wird vorausgesetzt, dass DNS für den Lastenausgleich des gesamten Datenverkehrs mit Ausnahme von Webdiensten verwendet wird. Im vorliegenden Beispiel gibt es drei Front-End-Server wie in der Tabelle gezeigt.
    
   |**Servername**|**Typ**|**Daten**|
   |:-----|:-----|:-----|
   |SFB01  <br/> |Host (A)  <br/> |10.0.0.5  <br/> |
   |SFB02  <br/> |Host (A)  <br/> |10.0.0.6  <br/> |
   |SFB03  <br/> |Host (A)  <br/> |10.0.0.7  <br/> |
   
7. Als Nächstes erstellen Sie die DNS-Lastenausgleichseinträge für den Pool. Der DNS-Lastenausgleich ermöglicht das Senden von Anforderungen durch DNS an die einzelnen Server im Pool unter Verwendung des gleichen DNS-Poolnamens. Weitere Informationen zu DNS und Lastenausgleich finden Sie unter [DNS-Anforderungen für Skype for Business Server](../../plan-your-deployment/network-requirements/dns.md). 
    
    > [!NOTE]
    > Nur in Enterprise Edition-Bereitstellungen können mehrere Server gepoolt werden. Wenn Sie einen einzelnen Enterprise-Server oder einen Standard Edition-Server bereitstellen, müssen Sie für diesen nur einen A-Eintrag erstellen. 
  
    Wenn Sie beispielsweise über einen Pool namens „pool.contoso.local“ und drei Front-End-Server verfügen, würden Sie die folgenden DNS-Einträge erstellen:
    
   |**FQDN**|**Typ**|**Daten**|
   |:-----|:-----|:-----|
   |pool.contoso.local  <br/> |Host (A)  <br/> |10.0.0.5  <br/> |
   |pool.contoso.local  <br/> |Host (A)  <br/> |10.0.0.6  <br/> |
   |pool.contoso.local  <br/> |Host (A)  <br/> |10.0.0.7  <br/> |
   
8. Fahren Sie mit der Erstellung von A-Einträgen für alle Server in der Bereitstellung fort. 
    
9. Zum Erstellen des SRV (Serviceeintrags) für die Vorgänger-Ermittlung klicken Sie mit der rechten Maustaste auf die SIP-Domäne und wählen Sie **Andere neue Einträge** aus.
    
10. Klicken Sie unter **Wählen Sie einen Ressourceneintragstyp** auf **Dienstidentifizierung (SRV)** und dann auf **Eintrag erstellen**.
    
11. Klicken Sie auf **Dienst** und geben Sie **_sipinternaltls** ein.
    
12. Klicken Sie auf **Protokoll** und geben Sie **_tcp** ein.
    
13. Klicken Sie auf **Portnummer** und geben Sie **5061** ein.
    
14. Klicken Sie auf **Host, der diesen Dienst anbietet** und geben Sie den FQDN des Pools bzw. des Standard Edition-Servers ein.
    
     ![Screenshot des Dialogs „Neuen Eintrag erstellen“](../../media/54b1aac5-a2ec-41fe-90c0-02eaeaa9d1b4.png)
  
15. Klicken Sie auf **OK** und dann auf **Fertig**.
    
### <a name="verify-dns-records"></a>Überprüfen von DNS-Einträgen

1. Melden Sie sich mit einem Konto, das Mitglied der Gruppe der authentifizierten Benutzer ist oder über gleichwertige Berechtigungen verfügt, an einem Clientcomputer in der Domäne an.
    
2. Klicken Sie auf **Start**, geben Sie **cmd** ein und drücken Sie die Eingabetaste.
    
3. Geben **Sie \<nslookup-FQDN des Front-\> End-Pools** oder ** \<des FQDN des Standard Edition-Servers oder\>des Enterprise Edition-Servers**ein, und drücken Sie die EINGABETASTE.
    
4. Fahren Sie mit der Überprüfung der restlichen A-Einträge der Bereitstellung fort.
    
5. Wenn Sie Vorgängerclients unterstützen und einen SRV-Eintrag erstellt haben, prüfen Sie diesen durch Eingabe von **set type=srv** an der **nslookup**-Eingabeaufforderung und Drücken der Eingabetaste.
    
6. Geben Sie **_sipinternaltls. _tcp ein. *Domäne* ** (Beispiel: _sipinternaltls. _tcp. contoso. local), und drücken Sie dann die EINGABETASTE.
    
7. Die Ausgabe sollte derjenigen in der Abbildung ähneln. In der Beispielausgabe werden nicht alle DNS-Einträge gezeigt, es müssen jedoch alle Einträge geprüft werden. 
    
     ![DNS-Einstellungen überprüfen](../../media/4fcaa70f-7717-4939-9652-d2048d6293cc.png)
  

