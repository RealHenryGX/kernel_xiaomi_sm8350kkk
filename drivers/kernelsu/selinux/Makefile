obj-y += selinux.o
obj-y += sepolicy.o
obj-y += rules.o

# This kernel provides both symbols (security/selinux/include/objsec.h has
# current_sid(), include/security.h has struct selinux_state), so KernelSU must
# NOT emit its pre-5.10 stand-ins.  The probe above is what upstream uses; it
# runs in a kbuild sub-make where $(srctree) is not what it expects, so state it
# outright - it was verified against this tree.
ccflags-y += -DKSU_COMPAT_HAS_CURRENT_SID
ccflags-y += -DKSU_COMPAT_HAS_SELINUX_STATE

ccflags-y += -Wno-implicit-function-declaration -Wno-strict-prototypes -Wno-int-conversion
ccflags-y += -Wno-declaration-after-statement -Wno-unused-function
ccflags-y += -I$(srctree)/security/selinux -I$(srctree)/security/selinux/include
ccflags-y += -I$(objtree)/security/selinux -include $(srctree)/include/uapi/asm-generic/errno.h
