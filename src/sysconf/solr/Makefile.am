###
###    Copyright (C) 2012 Huseyin Kerem Cevahir <kerem@mydlp.com>
###
###--------------------------------------------------------------------------
###    This file is part of MyDLP.
###
###    MyDLP is free software: you can redistribute it and/or modify
###    it under the terms of the GNU General Public License as published by
###    the Free Software Foundation, either version 3 of the License, or
###    (at your option) any later version.
###
###    MyDLP is distributed in the hope that it will be useful,
###    but WITHOUT ANY WARRANTY; without even the implied warranty of
###    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
###    GNU General Public License for more details.
###
###    You should have received a copy of the GNU General Public License
###    along with MyDLP.  If not, see <http://www.gnu.org/licenses/>.
###--------------------------------------------------------------------------

solrdir = $(datadir)/mydlp/solr

solr_DATA = \
	solr-4.2.0/dist/solr-4.2.0.war

solrlibdir = $(datadir)/mydlp/solr/lib

solrlib_DATA = \
	solr-4.2.0/dist/solr-cell-4.2.0.jar

backenddir = $(datadir)/mydlp/backend

solr-4.2.0.tgz:
	@$(WGET) -q http://ftp/ftp/mydlp/mydlp-distro/solr/solr-4.2.0.tgz

solr-4.2.0/dist/solr-4.2.0.war solr-4.2.0/dist/solr-cell-4.2.0.jar: solr-4.2.0.tgz
	@$(TAR) -zxf solr-4.2.0.tgz
	

install-data-hook:
	mkdir -p $(DESTDIR)$(solrdir) && \
		cp -af home/* $(DESTDIR)$(solrdir)/
	mkdir -p $(DESTDIR)$(solrlibdir) && \
		ln -s $(backenddir)/mydlp-backend.jar $(DESTDIR)$(solrlibdir)/mydlp-backend.jar
	mkdir -p $(DESTDIR)$(solrlibdir) && \
		ln -s $(backenddir)/tika-xps.jar $(DESTDIR)$(solrlibdir)/tika-xps.jar

