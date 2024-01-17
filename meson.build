project('nodm', 'c')

# check if we want PAM support (enabled by default)
disable_pam = get_option('disable_pam')

x11_dep = dependency('x11')

# make pam dependencies optional, meson will ignore non-found deps
if disable_pam
  pam_dep = dependency('pam', required: false)
  pam_misc_dep = dependency('pam_misc', required: false)
  extra_args = '-DNO_PAM'
else
  pam_dep = dependency('pam')
  pam_misc_dep = dependency('pam_misc')
  extra_args = ''
endif

executable('nodm', 'nodm.c',
                   'dm.c',
                   'common.c',
                   'log.c',
                   'vt.c',
                   'xserver.c',
                   'xsession.c',
                   'xsession-child.c',
                   dependencies: [x11_dep, pam_dep, pam_misc_dep],
                   install: true,
                   c_args: extra_args
)
