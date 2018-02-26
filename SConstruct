##############################
env_app = Environment(CCFLAGS = ['-g','-fsanitize=address','-fno-omit-frame-pointer'],
	LIBPATH = '.',
	LINKFLAGS = ['-rdynamic','-fsanitize=address'])
env_app.Append(CPPDEFINES = ['HAVE_CONFIG_H'])
env_app.Prepend(CPPPATH = ['.','lib'])
env_app.Append(LIBS = ['zebra','crypt','readline'])
####################################
lib_sources = Split("""
lib/network.c
lib/pid_output.c
lib/getopt.c
lib/getopt1.c
lib/daemon.c
lib/checksum.c
lib/vector.c
lib/linklist.c
lib/vty.c
lib/command.c
lib/sockunion.c
lib/prefix.c
lib/thread.c
lib/if.c
lib/memory.c
lib/buffer.c
lib/table.c
lib/hash.c
lib/filter.c
lib/routemap.c
lib/distribute.c
lib/stream.c
lib/str.c
lib/log.c
lib/plist.c
lib/zclient.c
lib/sockopt.c
lib/smux.c
lib/agentx.c
lib/snmp.c
lib/md5.c
lib/if_rmap.c
lib/keychain.c
lib/privs.c
lib/sigevent.c
lib/pqueue.c
lib/jhash.c
lib/memtypes.c
lib/workqueue.c
lib/vrf.c
lib/event_counter.c
lib/nexthop.c
""")
env_app.StaticLibrary('zebra', lib_sources)
################
env_app.Program('test_cli', ['vtysh/vtysh.c', 'vtysh/vtysh_main.c'])
############
