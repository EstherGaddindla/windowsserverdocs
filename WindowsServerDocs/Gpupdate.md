---
title: Gpupdate
ms.custom: na
ms.prod: windows-server-2012
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 2fd4e567-2ce1-4637-b611-c2f0895e5708
author: jaimeo
---
# Gpupdate
Updates Group Policy settings. For examples of how this command can be used, see [Examples](#BKMK_Examples).  
  
## Syntax  
  
```  
gpupdate [/target:{Computer | User}] [/force] [/wait:<VALUE>] [/logoff] [/boot] [/sync] [/?]  
```  
  
### Parameters  
  
|Parameter|Description|  
|-------------|---------------|  
|\/target:{Computer &#124; User}|Updates only User or only Computer policy settings.|  
|\/force|Reapplies all policy settings. By default, only policy settings that have changed are applied.|  
|\/wait:<VALUE>|Sets the number of seconds to wait for policy processing to finish before returning to the command prompt. When the time limit is exceeded, the command prompt appears, but policy processing continues. The default value is 600 seconds. The value **0** means not to wait. The value **\-1** means to wait indefinitely.<br /><br />In a script, by using this command with a time limit specified, you can run **gpupdate** and continue with commands that do not depend upon the completion of **gpupdate**. Alternatively, you can use this command with no time limit specified to let **gpupdate** finish running before other commands that depend on it are run.|  
|\/logoff|Causes a logoff after the Group Policy settings are updated. This is required for those Group Policy client\-side extensions that do not process policy on a background update cycle but do process policy when a user logs on. Examples include user\-targeted Software Installation and Folder Redirection. This option has no effect if there are no extensions called that require a logoff.|  
|\/boot|Causes a computer restart after the Group Policy settings are applied. This is required for those Group Policy client\-side extensions that do not process policy on a background update cycle but do process policy at computer startup. Examples include computer\-targeted Software Installation. This option has no effect if there are no extensions called that require a restart.|  
|\/sync|Causes the next foreground policy application to be done synchronously. Foreground policy is applied at computer boot and user logon. You can specify this for the user, computer, or both, by using the **\/target** parameter. The **\/force** and **\/wait** parameters are ignored if you specify them.|  
|\/?|Displays Help at the command prompt.|  
  
## Remarks  
  
-   The **gpupdate** command is available in [!INCLUDE[nextref_server_7](includes/nextref_server_7_md.md)], [!INCLUDE[nextref_longhorn](includes/nextref_longhorn_md.md)], [!INCLUDE[nextref_client_7ult](includes/nextref_client_7ult_md.md)], [!INCLUDE[nextref_client_7pro](includes/nextref_client_7pro_md.md)], [!INCLUDE[nextref_vistau](includes/nextref_vistau_md.md)], [!INCLUDE[nextref_vistae](includes/nextref_vistae_md.md)], and Windows Vista Business.  
  
## <a name="BKMK_Examples"></a>Examples  
Force a background update of all Group Policy settings, regardless of whether they have changed.  
  
```  
gpupdate /force  
```  
  
## Additional references  
  
-   [Group Policy TechCenter](http://go.microsoft.com/fwlink/?LinkID=145531)  
  
-   [Command-Line Syntax Key](Command-Line-Syntax-Key.md)  
  
