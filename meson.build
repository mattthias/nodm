project('nodm', 'c')

x11_dep = dependency('x11')
pam_dep = dependency('pam')
pam_misc_dep = dependency('pam_misc')


executable('nodm', 'nodm.c', 
                   'dm.c', 
                   'common.c', 
                   'log.c', 
                   'vt.c',
                   'xserver.c',
                   'xsession.c',
                   'xsession-child.c',
                   dependencies: [x11_dep, pam_dep, pam_misc_dep],
                   install: true
)



