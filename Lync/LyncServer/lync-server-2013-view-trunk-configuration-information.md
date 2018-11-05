---
title: Anzeigen von Informationen zur Trunkkonfiguration in Lync Server 2013
TOCTitle: Anzeigen von Informationen zur Trunkkonfiguration in Lync Server 2013
ms:assetid: ebe10e14-08c2-4797-9254-9ed89516d5cd
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721927(v=OCS.15)
ms:contentKeyID: 49890992
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen von Informationen zur Trunkkonfiguration in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

SIP-Trunk-Konfigurationseinstellungen definieren die Beziehung und die Funkionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Publich Switched Telephone Network, Festnetz), einer IP-Nebenstellenanlage (Public Branch Exchange, PBX) oder einem Session Border Controller (SBC) beim Dienstanbieter. Diese Einstellungen geben unter anderem Folgendes an:

  - Ob Medienumgehung für die Trunks aktiviert werden soll.

  - Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control Protocol) gesendet werden.

  - Ob SRTP-Verschlüsselung (Secure Real-Time Protocol) für jeden Trunk erforderlich ist.

Bei der Installation von Microsoft Lync Server 2013 wird eine globale Auflistung von SIP-Trunk-Konfigurationseinstellungen erstellt. Zusätzlich dazu können Administratoren benutzerdefinierte Auflistungen von Einstellungen auf Standortebene oder auf Dienstebene (nur für den PSTN-Gateway-Dienst) erstellen.

## Anzeigen von SIP-Trunk-Konfigurationsinformationen mithilfe der Lync Server-Systemsteuerung

1.  Klicken Sie in der Lync Server-Systemsteuerung auf **VoIP-Routing** und dann auf **Trunkkonfiguration**.

2.  Auf der Registgerkarte **Trunkkonfiguration** wird eine Liste aller Auflistungen von Trunk-Konfigurationseinstellungen angezeigt. Für jede Auflistung werden die Werte für die Eigenschaften **Name**, **Umfang**, **Status** und **Medienumgehung**, die Anzahl der PSTN-Verwendungen sowie die Regeln für anrufende Nummern und die Regeln für angerufene Nummern angezeigt. Wenn Sie zusätzliche Einzelheiten zu einer Auflistung von Trunk-Konfigurationseinstellungen benötigen, klicken Sie auf die betreffende Auflistung, dann auf **Bearbeiten** und anschließend auf **Details anzeigen**. Beachten Sie, dass Sie Einzelheiten immer nur für eine einzige Auflistung von Trunk-Konfigurationseinstellungen anzeigen können.

## Anzeigen von SIP-Trunk-Konfigurationsinformationen mithilfe von Lync Server PowerShell-Cmdlets

Sie können SIP-Trunk-Konfigurationseinstellungen auch mithilfe von Lync Server PowerShell und des **Get-CsTrunkConfiguration**-Cmdlets anzeigen. Dieses Cmdlet können Sie entweder in der Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausführen.

## Anzeigen von SIP-Trunk-Konfigurationsinformationen

  - Zum Anzeigen von Informationen zu allen SIP-Trunk-Konfigurationseinstellungen geben Sie den folgenden Befehl in der Lync Server-Verwaltungsshell ein, und drücken Sie die EINGABETASTE:
    
        Get-CsTrunkConfiguration
    
    Es werden etwa folgende Informationen zurückgegeben:
    
        Identity                                  : Global
        OutboundTranslationRulesList              : {}
        SipResponseCodeTranslationRulesList       : {}
        OutboundCallingNumberTranslationRulesList : {}
        PstnUsages                                : {}
        Description                               :
        ConcentratedTopology                      : True
        EnableBypass                              : False
        EnableMobileTrunkSupport                  : False
        EnableReferSupport                        : True
        EnableSessionTimer                        : False
        EnableSignalBoost                         : False
        MaxEarlyDialogs                           : 20
        RemovePlusFromUri                         : False
        RTCPActiveCalls                           : True
        RTCPCallsOnHold                           : True
        SRTPMode                                  : Required
        EnablePIDFLOSupport                       : False
        EnableRTPLatching                         : False
        EnableOnlineVoice                         : False
        ForwardCallHistory                        : False
        Enable3pccRefer                           : False
        ForwardPAI                                : False
        EnableFastFailoverTimer                   : True

Weitere Informationen finden Sie in dem Hilfethema zum [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration)-Cmdlet.

