package /* Your Page */

import org.bukkit.entity.Player;
import org.bukkit.event.player.AsyncPlayerChatEvent;
import org.bukkit.plugin.java.JavaPlugin;

public class ASYNCCHAT {
	private String CHAT_HEAD;
	private String CHAT_COLOR_SPZIAL;
	private String CHAT_COLOR_NORMAL;
	private JavaPlugin plugin;
	
	public ASYNCCHAT(String cmd, JavaPlugin plugin){
		this.plugin = plugin;
		if(cmd.equalsIgnoreCase("init")){
			/* Initialization */
			
			/* USE:
			 * 	>>%rn: Rangname
			 *  -%rc: Rangfarbe
			 *  >>%ms: Nachricht
			 *  >>%se: Spieler der Naricht
			 *  >>%ct: Farbe der Naricht (s. [a1])
			 */
			CHAT_HEAD = "%rc%rn §8❘ %rc%se §8» %ct%ms";
					
			/* [a1]
			 *  Narichten Farben
			 */
			CHAT_COLOR_SPZIAL = ""; // « Admins
			CHAT_COLOR_NORMAL = ""; // « Normale
		}
	}
	public void UpdateFormat(String format){
		CHAT_HEAD = format;
	}
	public String GetFormat(){
		return CHAT_HEAD;
	}
	public AsyncPlayerChatEvent Run(AsyncPlayerChatEvent event){
		String NEW_HEAD = CHAT_HEAD;
		Player p = event.getPlayer();
		if(p.hasPermission("System.Admin")){
			NEW_HEAD = NEW_HEAD.replaceAll("%ct", CHAT_COLOR_SPZIAL);
		}else{
			NEW_HEAD = NEW_HEAD.replaceAll("%ct", CHAT_COLOR_NORMAL);
		}
		NEW_HEAD = NEW_HEAD.replaceAll("%ms", event.getMessage());
		NEW_HEAD = NEW_HEAD.replaceAll("%se", p.getName());
		NEW_HEAD = NEW_HEAD.replaceAll("%rn", getRangName(p));
		NEW_HEAD = NEW_HEAD.replaceAll("%rc", getRangFarbe(p));
		
		/* Naricht Posten */
		for(Player all : plugin.getServer().getOnlinePlayers()){
			all.sendMessage(NEW_HEAD);
		}
		
		/* Werte Zurueckgeben */
		event.setCancelled(true);
		return event;
	}
	
	/* RangNamen */
	private static final String getRangName(Player p){
		if(p.hasPermission("system.admin")){
			return "Administrator";
		}
		if(p.hasPermission("System.community")){
			return "Community";
		}
		if(p.hasPermission("System.SrDev")){
			return "SrDeveloper";
		}
		if(p.hasPermission("System.SrMod")){
			return "SrModerator";
		}
		if(p.hasPermission("System.Mod")){
			return "Moderator";
		}
		if(p.hasPermission("System.Dev")){
			return "Developer";
		}
		if(p.hasPermission("System.SrBuilder")){
			return "SrBuilder";
		}
		if(p.hasPermission("System.Builder")){
			return "Builder";
		}
		if(p.hasPermission("System.YouTuber")){
			return "YouTuber";
		}
		if(p.hasPermission("System.Streamer")){
			return "Streamer";
		}
		if(p.hasPermission("System.Premium+")){
			return "Premium+";
		}
		if(p.hasPermission("System.Supp")){
			return "Supporter";
		}
		if(p.hasPermission("System.Premium")){
			return "Premium";
		}
		return "Spieler";
	}
	
	/* RangFarben */
	private static final String getRangFarbe(Player p){
		if(p.hasPermission("system.admin")){
			return "§4";
		}
		if(p.hasPermission("System.community")){
			return "§a";
		}
		if(p.hasPermission("System.SrDev")){
			return "§b";
		}
		if(p.hasPermission("System.SrMod")){
			return "§c";
		}
		if(p.hasPermission("System.Mod")){
			return "§c";
		}
		if(p.hasPermission("System.Dev")){
			return "§b";
		}
		if(p.hasPermission("System.SrBuilder")){
			return "§e";
		}
		if(p.hasPermission("System.Builder")){
			return "§e";
		}
		if(p.hasPermission("System.YouTuber")){
			return "§5";
		}
		if(p.hasPermission("System.Streamer")){
			return "§5";
		}
		if(p.hasPermission("System.Premium+")){
			return "§6";
		}
		if(p.hasPermission("System.Supp")){
			return "§9";
		}
		if(p.hasPermission("System.Premium")){
			return "§6";
		}
		return "§7";
	}
}
