# Customization for ZAP DAQ

Copy the scripts from bin to ~/bin

```
./install
```

Create a link to the CURRENT fleet, eg ZAP318:

```
cd ~/bin; ln -s ZAP318 ZAP_CURRENT
```

Sample cs-studio workspace (works with cs-studio 4.5.9)
This may work for with an unknown user, however what may be more successful 
would be to create a workspace according to the README in ACQ400CSS, then update the prefs files:

```
CSS-Workspaces/zap318/.metadata/.plugins/org.eclipse.core.runtime/.settings/org.csstudio.diirt.util.core.preferences.prefs
CSS-Workspaces/zap318/.metadata/.plugins/org.eclipse.core.runtime/.settings/org.csstudio.opibuilder.prefs
```

This may be quicker than setting macros in a dialog.

## org.csstudio.diirt.util.core.preferences.prefs

```
diirt.ca.addr.list=acq2106_318 acq2106_317 acq2106_316 acq2106_315 acq2106_314 acq2106_313 acq2106_307 acq2106_306
diirt.ca.auto.addr.list=false
diirt.ca.max.array.size=500000
diirt.default.initialized=true
eclipse.preferences.version=1
```

It _may_ be necessary to set an address list IF the network is hostile to EPICS name service resolution (eg if using a VPN). The names must be valid DNS names (set in /etc/hosts if no dynamic DNS on site.


## CSS-Workspaces/zap318/.metadata/.plugins/org.eclipse.core.runtime/.settings/org.csstudio.opibuilder.prefs
```
macros="UUT","acq2106_318"|"UUT1","acq2106_318"|"UUT2","acq2106_317"|"UUT3","acq2106_316"|"UUT4","acq2106_315"|"UUT5","acq2106_314"|"UUT6","acq2106_313"|"UUT7","acq2106_307"|"UUT8","acq2106_306"|"CAPOPI","capture"|"LAUNCHOPI","../ACQ400_LAUNCHER"
```

