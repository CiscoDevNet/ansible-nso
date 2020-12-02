==========================================
Cisco NSO Ansible Collection Release Notes
==========================================

.. contents:: Topics


v1.0.2
======

Minor Changes
-------------

- add GitHub Action to the repo for automated sanity and unit tests
- minor fixes to prepare for inclusion in Ansible 2.10

v1.0.1
======

Minor Changes
-------------

- Added See Also section to docs providing links to additional resources
- Added example for nso_action
- Corrected import paths in the test modules
- Defined data types for arguments in the docs where necessary to pass sanity tests
- Existing nso_config L3VPN example replaced with new examples due to existing example reliance on non-default l3vpn module
- Modified nso_verify module example
- Updated documentation with a See Also section providing links to NSO resources
- Updated examples for nso_show
- Updated examples in the documentation to align with the NSO DevNet Sandbox
- Verified all sanity and unit tests passing

v1.0.0
======

Release Summary
---------------

This is the first release of the ``cisco.nso`` collection. The modules in this collection were migrated from Ansible Core with no changes to their functionality.
