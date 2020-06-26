# OpenSCAP

Fedora based (docker pull fedora:32), installed with podman and oscap-podman applications to perform vulnerability and policy compliance scans.

## Testing
To test that the container works, run 'podman info' inside the container. 
It may be possible to receive an overlay error.

## Directions
This section will be filled out in the near future.

## Example Code
Pull container into podman container repository:

'''
podman pull ubi8
'''

Perform CVE scan on a container:

'''
oscap-podman $(podman images | grep ubi | awk '{print $3}') oval eval --report vulnerability.html ssg-rhel8-oval.xml
'''
NOTE: oscap-podman uses container ID's when performing scans. The above example lists available containers in the podman container repository, filters an image named 'ubi', and then passes the container ID to oscap-podman to use. The scan is performed using data in 'ssg-rhel8-oval.xml' - located in /usr/share/xml/ssg/content - as a basis and generates the scan report 'vulnerability.html' to view in a web browser.
